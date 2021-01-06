# join

## join(other, on=None, how=None)：根据提供的表达式与另一个DataFrame做连接  
other: 另一个DataFrame  
on: 字符串或字符串序列，表达式或表达式序列  
how: 字符串，默认inner，必须：inner, cross, outer, full, fullouter, full_outer, left, leftouter, left_outer, right, rightouter, right_outer, semi, leftsemi, left_semi, anti, leftanti and left_anti  
```python
# 假如有如下2个DataFrame
'''
df1:
+-----+----+
|name1|age1|
+-----+----+
|    a|  11|
|    b|  21|
|    c|  31|
+-----+----+

df2:
+-----+----+
|name2|age2|
+-----+----+
|    b|  22|
|    c|  32|
|    d|  32|
+-----+----+
'''
```
### 连接条件
```python
# 表达式
df_join1 = df1.join(df2, df1.name1==df2.name2)
df_join1.show()
'''
+-----+----+-----+----+
|name1|age1|name2|age2|
+-----+----+-----+----+
|    c|  31|    c|  32|
|    b|  21|    b|  22|
+-----+----+-----+----+
'''

# 其他形式：
# 表达式序列：df_join2 = df1.join(df2, [df1.name1==df2.name2, df1.age1==df2.age2])
# 字符串：df_join3 = df1.join(df2, "name") # 2个df中均必须存在字段name
# 字符串序列：df_join3 = df1.join(df2, ["name","age"]) # 2个df中均必须存在字段name,age

```
### 左连接
```python
df_join3 = df1.join(df2, df1.name1==df2.name2, "left")
df_join3.show()
'''
+-----+----+-----+----+
|name1|age1|name2|age2|
+-----+----+-----+----+
|    c|  31|    c|  32|
|    b|  21|    b|  21|
|    a|  11| null|null|
+-----+----+-----+----+
'''
```


