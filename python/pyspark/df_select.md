# select/selectExpr

## select(*cols)：选取字段并返回DataFrame
```python
df = spark.createDataFrame([("a", 22, 165), ("b", 23, 168), ("c",  25, 176)], ["name", "age", "height"])

# 选取某个字段
df1 = df.select("age")
df1.show()
'''
+---+
|age|
+---+
| 22|
| 23|
| 25|
+---+
'''

# 选取多个字段
df2 = df.select("age", "name")
df2.show()
'''
+---+----+
|age|name|
+---+----+
| 22|   a|
| 23|   b|
| 25|   c|
+---+----+
'''

# 表达式选取
df3 = df.select("name", (df.age+10).alias("age"))
df3.show()
'''
+----+---+
|name|age|
+----+---+
|   a| 32|
|   b| 33|
|   c| 35|
+----+---+
'''
```

## selectExpr(*expr)：支持SQL表达式选择并返回DataFrame
```python
df4 = df.selectExpr("max(age) a", "min(height) h")
df4.show()
'''
+---+---+
|  a|  h|
+---+---+
| 25|165|
+---+---+
'''
df5 = df.selectExpr("age * 2 age1", "abs(height) abs")
df5.show()
'''
+----+---+
|age1|abs|
+----+---+
|  44|165|
|  46|168|
|  50|176|
+----+---+
'''
```
