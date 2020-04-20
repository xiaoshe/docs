# 集合操作

## 创建
```python
x = set()
# 或
x = {1} # 必须有值，否则为dict

# 注意以下几种不同：
x = set("red")     # x: {'e', 'd', 'r'}
x = set("red",)    # x: {'e', 'd', 'r'}
x = set(("red"))   # x: {'e', 'd', 'r'}
x = set(("red",))  # x: {'red'}
x = {"red"}        # x: {'red'}

# 也可以直接传入元组
a = ["red","red","black"]
x = set(a)     # x: {'black', 'red'}
```

## 添加
x.add(value) # 添加一个元素
或
x.update() # 添加多个元素，可以是元组，字典，列表

```python
x = {"red"}
x.update(["black", "blue"])  # x: {'red', 'blue', 'black'}
x.update({"yellow":123})     # x: {'blue', 'red', 'black', 'yellow'}
```

## 移出元素
x.remove(v)  # 元素v不存在时报错
或
x.discard(v) # 元素v不存在时也不报错
或
v = x.pop()  # 随机删除一个元素

## 元素个数
len(x)

## 判断元素是否在集合中
v in x

## 清空集合
x.clear()

## 交集
```python
# 后面操作依然使用x和y
x = {1,2,3,4}
y = {3,4,5,6,7}

ret = x & y
# 或
ret = x.intersection(y)

# 输出ret:{3, 4}
```

## 并集
```python
ret = x | y
# 或
ret = x.union(y)

# 输出ret:{1, 2, 3, 4, 5, 6, 7}
```

## 差集
```python
ret = x - y  # 在x中但不在y中的
# 或
ret = x.difference(y)

# 输出ret:{1, 2}

ret = y - x  # 在y中但不在x中的
# 或
ret = y.difference(x)

# 输出ret:{5, 6, 7}
```

## 对称差集
去掉相同元素后的集合
```python
ret = x ^ y
# 或
ret = x.symmetric_difference(y)
# 输出ret:{1, 2, 5, 6, 7}

# x ^ y 与 y ^ x 等价

ret = {1,2,3} ^ {2,3}
# 输出ret:{1}
```

## 子集和超集
如果x包含y的所有元素，则x是y的超集，y是x的子集  
子集：x.issubset(y), x是y的子集  
超集：x.issuperset(y), x是y的超集
```python
{1}.issubset({1,2}) # True
{1,2,3}.issubset({1,2}) # False

{1,2,3}.issuperset({1,2}) # True
```


