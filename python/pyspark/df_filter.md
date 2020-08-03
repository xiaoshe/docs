# filter/where

## filter(condition)：根据给定条件按行选取，不修改原DataFrame
```python
df = spark.createDataFrame([("a", 22, 165), ("b", 23, 168), ("c",  25, 176)], ["name", "age", "height"])
df.show()
'''
+----+---+------+
|name|age|height|
+----+---+------+
|   a| 22|   165|
|   b| 23|   168|
|   c| 25|   176|
+----+---+------+
'''

# 选取age>22的数据
df1 = df.filter("age>22")
df1.show()
'''
+----+---+------+
|name|age|height|
+----+---+------+
|   b| 23|   168|
|   c| 25|   176|
+----+---+------+
'''
df2 = df.filter(df.age > 22)
# df2等价与df1

# 多个条件选取
df3 = df.filter("age>22 and height>170")
df3.show()
'''
+----+---+------+
|name|age|height|
+----+---+------+
|   c| 25|   176|
+----+---+------+
'''
df4 = df.filter((df.age>22) & (df.height>170))
# df4与df3等价，需要注意的是：每个条件都需要()扩起来
```

## where：filter的别名
