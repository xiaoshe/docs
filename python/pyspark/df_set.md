# 集合操作：交集、并集、差集

```python
# 集合操作，差并交
a = spark.createDataFrame([("a",), ("b",), ("c",), ("d",)], ["name"])
a.show()
'''
+----+
|name|
+----+
|   a|
|   b|
|   c|
|   d|
+----+
'''
b = spark.createDataFrame([("b",), ("f",), ("c",), ("e",)], ["name"])
b.show()
'''
+----+
|name|
+----+
|   b|
|   f|
|   c|
|   e|
+----+
'''

# 差集：a - b
c = a.subtract(b)
c.show()
'''
+----+
|name|
+----+
|   d|
|   a|
+----+
'''

# 交集：a & b
c = a.intersect(b)
c.show()
'''
+----+
|name|
+----+
|   c|
|   b|
+----+
'''

# 并集：a | b，union后去重
c = a.union(b).distinct()
c.show()
'''
+----+
|name|
+----+
|   f|
|   e|
|   d|
|   c|
|   b|
|   a|
+----+
'''
```
