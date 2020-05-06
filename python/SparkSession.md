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

```python
class SparkSession:
	builder = Builder()
	def newSession(self):
	def sparkContext(self):
	def version(self):
	def conf(self):
	def catalog(self):
	def udf(self):
	def range(self, start, end=None, step=1, numPartitions=None):
	def createDataFrame(self, data, schema=None, samplingRatio=None, verifySchema=True):
	def sql(self, sqlQuery):
	def table(self, tableName):
	def read(self):
	def readStream(self):
	def streams(self):
	def stop(self):
```

```python
class Builder:
	# 设置配置项，config(key="", value="") or config(conf=SparkConf())
	def config(self, key=None, value=None, conf=None):

	# 设置连接那个集群，"local"本地执行，"local[4]"本地4核执行
	def master(self, master):
		return self.config("spark.master", master)

	# 设置应用名称，用于web显示
	def appName(self, name):
		return self.config("spark.app.name", name)

	# 支持hive
	def enableHiveSupport(self):
		return self.config("spark.sql.catalogImplementation", "hive")
	
	# 首先检查全局默认SparkSession是否存在，如果存在则返回该SparkSession，否则创建后返回
	# 全局只有一个SparkSession
	def getOrCreate(self):
```
### 简单使用
```python
spark = SparkSession.builder.appName("x").getOrCreate()
```


## SparkContext与SparkSession
SparkSession是Spark2.x后引入的概念。在2.x之前，对于不同的功能，需要使用不同的Context——  

- 创建和操作RDD时，使用SparkContext
- 使用Streaming时，使用StreamingContext
- 使用SQL时，使用sqlContext
- 使用Hive时，使用HiveContext

在2.x中，为了统一上述的Context，引入SparkSession，实质上是SQLContext、HiveContext、SparkContext的组合。  

参考: [https://blog.csdn.net/qq_36153312/article/details/98963236](https://blog.csdn.net/qq_36153312/article/details/98963236)


