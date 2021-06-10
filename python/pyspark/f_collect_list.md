# collect_list
### 聚合函数，将多个字段聚合成一个结构体字段

```python
df = spark.createDataFrame([("A","微信",200), ("A","抖音",120), ("A","王者",300), ("B","抖音",250),("B","王者",400)], ["user","app","time"])
df.show(truncate=False)
'''
+----+----+----+
|user|app |time|
+----+----+----+
|A   |微信|200 |
|A   |抖音|120 |
|A   |王者|300 |
|B   |抖音|250 |
|B   |王者|400 |
+----+----+----+
'''
# 按用户聚合
from pyspark.sql import functions as F
df = df.groupBy(['user']).agg(F.collect_list(F.struct('app','time')).alias('apps'))
df.show(truncate=False)
'''
+----+---------------------------------------+
|user|apps                                   |
+----+---------------------------------------+
|B   |[[抖音, 250], [王者, 400]]             |
|A   |[[微信, 200], [抖音, 120], [王者, 300]]|
+----+---------------------------------------+
'''
df.printSchema()
'''
root
 |-- user: string (nullable = true)
 |-- apps: array (nullable = true)
 |    |-- element: struct (containsNull = true)
 |    |    |-- app: string (nullable = true)
 |    |    |-- time: long (nullable = true)
'''
```

### 使用聚合字段有2种
```python
def m1(r):
    ret = ""
    for app,time in r.apps:
        ret += "{}{},".format(app, time)
    return r.user, ret,
df1 = df.rdd.map(m1).toDF()
df1.show(truncate=False)
'''
+---+------------------------+
|_1 |_2                      |
+---+------------------------+
|B  |抖音250,王者400,        |
|A  |微信200,抖音120,王者300,|
+---+------------------------+
'''

def m2(r):
    ret = ""
    for x in r.apps:
        ret += "{}{},".format(x.app, x.time)
    return r.user, ret,

df2 = df.rdd.map(m2).toDF()
df2.show(truncate=False)
'''
+---+------------------------+
|_1 |_2                      |
+---+------------------------+
|B  |抖音250,王者400,        |
|A  |微信200,抖音120,王者300,|
+---+------------------------+
'''
```
### 有无struct的区别
```python
# 有struct
df1 = df.groupBy(['user']).agg(F.collect_list(F.struct('app')).alias('apps'))
df1.show(truncate=False)
+----+------------------------+
|user|apps                    |
+----+------------------------+
|B   |[[抖音], [王者]]        |
|A   |[[微信], [抖音], [王者]]|
+----+------------------------+

# 无struct
df2 = df.groupBy(['user']).agg(F.collect_list('app').alias('apps'))
df2.show(truncate=False)
+----+------------------+
|user|apps              |
+----+------------------+
|B   |[抖音, 王者]      |
|A   |[微信, 抖音, 王者]|
+----+------------------+
```
