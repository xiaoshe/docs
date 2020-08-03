# 字段操作：增加、删除、重命名

## 增加字段withColumn(colName, col)
添加新字段或替换已有字段并返回一个DataFrame，参数col必须是Column类型  

```python
# 添加一个新字段
df = spark.createDataFrame([(10, 1), (11, 2), (12,  3), (12,  2)], ["sum", "cnt"])
df.show()
df2 = df.withColumn("avg", df.sum/df.cnt)
df2.show()

'''
+---+---+
|sum|cnt|
+---+---+
| 10|  1|
| 11|  2|
| 12|  3|
| 12|  2|
+---+---+

+---+---+----+
|sum|cnt| avg|
+---+---+----+
| 10|  1|10.0|
| 11|  2| 5.5|
| 12|  3| 4.0|
| 12|  2| 6.0|
+---+---+----+
'''
```

```python
# 修改已存在字段
df3 = df.withColumn("cnt", df.cnt + 1)
df3.show()
'''
+---+---+
|sum|cnt|
+---+---+
| 10|  2|
| 11|  3|
| 12|  4|
| 12|  3|
+---+---+
'''
```

```python
# 添加一个新字段，并设置默认值
from pyspark.sql.functions import lit
df4 = df.withColumn("day", lit("20200701"))
df4.show()
'''
+---+---+--------+
|sum|cnt|     day|
+---+---+--------+
| 10|  1|20200701|
| 11|  2|20200701|
| 12|  3|20200701|
| 12|  2|20200701|
+---+---+--------+
'''
```

```python
# 添加新字段：数组/map/struct类型
from pyspark.sql.functions import array, create_map, struct

df5 = df.withColumn("some_array", array(lit(1), lit(2), lit(3))) \
    .withColumn("some_struct", struct(lit("foo"), lit(1), lit(.3))) \
    .withColumn("some_map", create_map(lit("key1"), lit(1), lit("key2"), lit(2)))
df5.show()
'''
+---+---+----------+-------------+--------------------+
|sum|cnt|some_array|  some_struct|            some_map|
+---+---+----------+-------------+--------------------+
| 10|  1| [1, 2, 3]|[foo, 1, 0.3]|[key1 -> 1, key2 ...|
| 11|  2| [1, 2, 3]|[foo, 1, 0.3]|[key1 -> 1, key2 ...|
| 12|  3| [1, 2, 3]|[foo, 1, 0.3]|[key1 -> 1, key2 ...|
| 12|  2| [1, 2, 3]|[foo, 1, 0.3]|[key1 -> 1, key2 ...|
+---+---+----------+-------------+--------------------+
'''
```

## 字段重命名withColumnRenamed(existing, new)
将字段existing重命名为new，并将返回一个DataFrame。如果existing字段不存在，则操作无效。
```python
df = spark.createDataFrame([("a", 1), ("b", 2), ("c",  3)], ["name", "age"])
df1 = df.withColumnRenamed("age", "age1")
df1.show()
'''
+----+----+
|name|age1|
+----+----+
|   a|   1|
|   b|   2|
|   c|   3|
+----+----+
'''
```

## 删除字段drop(*cols)
删除指定的字段，并返回一个DataFrame，如果给定字段不存在，则不删除该字段
```python
df = spark.createDataFrame([("a", 22, 165), ("b", 23, 168), ("c",  25, 176)], ["name", "age", "height"])
df1 = df.drop("age", "age1")
df1.show()
'''
+----+------+
|name|height|
+----+------+
|   a|   165|
|   b|   168|
|   c|   176|
+----+------+
'''
```
