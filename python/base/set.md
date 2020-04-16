# 集合操作

## 创建
x = set()
或
x = {1} # 必须有值，否则为dict

## 添加
x.add(value)


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


