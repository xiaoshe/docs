# DataFrame简单使用

### 创建
##### 通过二维数组创建
```python
df = spark.createDataFrame([("a", 1), ("b", 2), ("c",  3), ("d",  2)], ["name", "age"])
```

##### 读取parquet文件创建
```python
df = spark.read.parquet(path)
df.show()
```
+----+---+
|name|age|
+----+---+
|   a|  1|
|   b|  2|
|   c|  3|
|   d|  2|
+----+---+


##### 使用sql操作DataFrame
```python
df.createOrReplaceTempView("t")
df2 = spark.sql("select * from t where age=2")
df2.show()
```
+----+---+
|name|age|
+----+---+
|   b|  2|
|   d|  2|
+----+---+
# registerTempTable也可以，但2.0已弃用，所以建议使用createOrReplaceTempView。

##### 封装，读parquet文件并使用sql操作
```python
def read_from_parquet(spark, path, sql, table_name):
    df = spark.read.parquet(path)
    df.createOrReplaceTempView(table_name)
    return spark.sql(sql)
df3 = read_from_parquet(spark, "output", "select * from t where age=2", "t")

```

### 保存
```python
# 保存为parquet文件
df.repartition(1).write.parquet(path="output", mode="overwrite")
# repartition：文件个数
# mode：模式，overwrite：覆盖写入；append：追加写入


# 保存为csv文件
df.repartition(1).write.csv(path="output2", mode="append", sep='\t')
# sep：字段分隔符，默认逗号','

```
