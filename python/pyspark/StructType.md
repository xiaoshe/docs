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
