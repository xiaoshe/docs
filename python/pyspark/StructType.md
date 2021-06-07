# StructType
pyspark.sql.types.StructType，由多个StructField组成  

StructField(name, dataType, nullable=True, metadata=None)  
常用dataType：  
- StringType
- BooleanType
- DoubleType
- FloatType
- ByteType
- IntegerType
- LongType
- ArrayType

nullable: 
- True: 允许字段为null（None）
- False：不允许字段为null（None）

### 例如
```python
from pyspark.sql.types import *
schema = StructType([
            StructField('name', StringType(), False),
            StructField('age', IntegerType(), False),
        ])
```

### ArrayType(dataType, nullable=True)
```python
schema = StructType([
            StructField('name', StringType(), False),
            StructField('tag', ArrayType(IntegerType(), False), False),
        ])
df = spark.createDataFrame([("a", [1]), ("b", [1,2]), ("c",  [1,2,3]), ("d", [1,2,3,4])], schema=schema)
df.show()
+----+------------+
|name|         tag|
+----+------------+
|   a|         [1]|
|   b|      [1, 2]|
|   c|   [1, 2, 3]|
|   d|[1, 2, 3, 4]|
+----+------------+
```
