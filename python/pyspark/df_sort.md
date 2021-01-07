# sort/orderBy

## sort(*cols, **kwargs) 排序指定列并返回一个DataFrame  
cols: Column列表或字段列表    
```python
# 假如有如下DataFrame
'''
df:
+----+---+
|name|age|
+----+---+
|   a| 11|
|   b|  2|
|   c|  3|
|   b|  3|
|   c|  6|
+----+---+
'''
# age降序
df.sort(df.age.desc()).show()
df.sort("age", ascending=False).show()
from pyspark.sql.functions import *
df.sort(desc("age")).show()  # 如果是asc可忽略

# age降序，name升序
df.sort([df.age.desc(), df.name.asc()]).show()   # []可要可不要
df.sort(["age", "name"], ascending=[0, 1]).show()
from pyspark.sql.functions import *
df.sort([desc("age"), asc("name")]).show()       # []可要可不要
df.sort([desc("age"), "name"]).show() 
```
## orderBy(*cols, **kwargs) 同sort
