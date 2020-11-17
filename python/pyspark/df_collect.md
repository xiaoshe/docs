# collect

## collect:返回所有行数据
函数会收集所有数据到driver上，在数据很大的情况下，请注意内存是否足够。
```python
df = spark.createDataFrame([("a", 22, 165), ("b", 23, 168), ("c",  25, 176)], ["name", "age", "height"])
df.collect()
'''
[Row(name='a', age=22, height=165),
 Row(name='b', age=23, height=168),
 Row(name='c', age=25, height=176)]
'''
# 或
for name,age,height in df.collect():
    print(name,age,height)
'''
a 22 165
b 23 168
c 25 176
'''
```

## first:返回第一行数据
```python
name,age,height = df.first()
# 返回：a 22 165
```
## head(n):返回前n行数据，n默认1。
如果n>1返回一个list，格式同collect()；如果n=1，返回一行数据，同first()。注意driver内存。

## tail(n):返回最后n行数据，3.0版本才有

## take(n):返回前n行数据，n必须


