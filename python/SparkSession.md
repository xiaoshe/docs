# SparkSession

SparkSession是执行spark使用DataSet或DataFrame的入口。  
使用SparkSession可以创建DataFrame、将DataFrame注册为table、在table上执行sql、缓存table、读取parquet文件，使用如下：
```python
>>> spark = SparkSession.builder \
...     .master("local") \
...     .appName("Word Count") \
...     .config("spark.some.config.option", "some-value") \
...     .getOrCreate()
```

## SparkContext与SparkSession
SparkSession是Spark2.x后引入的概念。在2.x之前，对于不同的功能，需要使用不同的Context——  

- 创建和操作RDD时，使用SparkContext
- 使用Streaming时，使用StreamingContext
- 使用SQL时，使用sqlContext
- 使用Hive时，使用HiveContext

在2.x中，为了统一上述的Context，引入SparkSession，实质上是SQLContext、HiveContext、SparkContext的组合。  

参考: [https://blog.csdn.net/qq_36153312/article/details/98963236](https://blog.csdn.net/qq_36153312/article/details/98963236)


