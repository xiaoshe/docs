# DataFrame简单使用

### 1 创建
##### 1.1 通过二维数组创建
```python
df = spark.createDataFrame([("a", 1), ("b", 2), ("c",  3), ("d",  2)], ["name", "age"])
```

##### 1.2 读取parquet文件创建
```python
df = spark.read.parquet(path)
df.show()
'''
+----+---+
|name|age|
+----+---+
|   a|  1|
|   b|  2|
|   c|  3|
|   d|  2|
+----+---+
'''
```

##### 1.3 使用sql操作DataFrame
```python
df.createOrReplaceTempView("t")
# registerTempTable也可以，但2.0已弃用，所以建议使用createOrReplaceTempView
df2 = spark.sql("select * from t where age=2")
df2.show()
'''
+----+---+
|name|age|
+----+---+
|   b|  2|
|   d|  2|
+----+---+
'''
```

##### 1.4 封装，读parquet文件并使用sql操作
```python
def read_from_parquet(spark, path, sql, table_name):
    df = spark.read.parquet(path)
    df.createOrReplaceTempView(table_name)
    return spark.sql(sql)
df3 = read_from_parquet(spark, "output", "select * from t where age=2", "t")

```

### 2 保存
调用pyspark.sql.DataFrameWriter，
```python
# 覆盖写入output，格式为parquet
df.repartition(1).write.format("parquet").mode("overwrite").save("output")
# 或
# 追加写入output，格式为csv
df.repartition(1).write.save(format="csv", mode="append", path="output")
```
format(f):json/parquet/csv/jdbc  
mode(saveMode):  
- overwrite: 覆盖写入
- append: 追加写入
- ignore: 数据存在则不写
- error/errorifexists: 数据存在则报错


除了上述写入方式外，还有以下几种：
##### 2.1 保存为parquet文件
```python
df.repartition(1).write.parquet(path="output", mode="overwrite")
# repartition：文件个数
```

##### 2.2 保存为csv文件
```python
df.repartition(1).write.csv(path="output2", mode="append", sep='\t')
# sep：字段分隔符，默认逗号','
```

##### 2.3 保存为json文件
```python
df.repartition(1).write.json(path="output", mode="overwrite")
文件内容：
{"name":"a","age":1}
{"name":"b","age":2}
{"name":"c","age":3}
{"name":"d","age":2}
```
