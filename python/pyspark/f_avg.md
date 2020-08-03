# count,sum,avg,min,max

## 1，使用agg
```python
from pyspark.sql import functions as F
df = spark.createDataFrame([(200,), (300,), (100,), (400,), (300,)], ["t"])
df.show()
'''
+---+
|  t|
+---+
|200|
|300|
|100|
|400|
|300|
+---+
'''
df.agg(F.avg("t").alias("avg"), # 平均值
       F.count("t").alias("count"), # 个数
       F.countDistinct("t").alias("countDistinct"), # 去重后个数
       F.sum("t").alias("sum"), # 和
       F.sumDistinct("t").alias("sumDistinct"), # 去重后求和
       F.min("t").alias("min"), # 最小值
       F.max("t").alias("max"), # 最大值
       F.mean("t").alias("mean") # 平均值
      ).show()
# agg可换成select
'''
+-----+-----+-------------+----+-----------+---+---+-----+
|  avg|count|countDistinct| sum|sumDistinct|min|max| mean|
+-----+-----+-------------+----+-----------+---+---+-----+
|260.0|    5|            4|1300|       1000|100|400|260.0|
+-----+-----+-------------+----+-----------+---+---+-----+
'''
```

## 2，使用selectExpr
```python
df.selectExpr("avg(t) avg", "count(t) count", 
              "count(distinct t) countDistinct", 
              "sum(t) sum", "sum(distinct t) sumDistinct",
              "min(t) min", "max(t) max").show()
'''
+-----+-----+-------------+----+-----------+---+---+-----+
|  avg|count|countDistinct| sum|sumDistinct|min|max| mean|
+-----+-----+-------------+----+-----------+---+---+-----+
|260.0|    5|            4|1300|       1000|100|400|260.0|
+-----+-----+-------------+----+-----------+---+---+-----+
'''
```
## 3，使用describe
```python
# 计算数量、均值、方差、最大、最小
df.describe("t").show()
'''
+-------+-----------------+
|summary|                t|
+-------+-----------------+
|  count|                5|
|   mean|            280.0|
| stddev|83.66600265340755|
|    min|              200|
|    max|              400|
+-------+-----------------+
'''
```
