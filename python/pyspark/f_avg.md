# count,sum,avg,min,max

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
'''
+-----+-----+-------------+----+-----------+---+---+-----+
|  avg|count|countDistinct| sum|sumDistinct|min|max| mean|
+-----+-----+-------------+----+-----------+---+---+-----+
|260.0|    5|            4|1300|       1000|100|400|260.0|
+-----+-----+-------------+----+-----------+---+---+-----+
'''
```
