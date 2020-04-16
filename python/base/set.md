# 集合操作

## 创建
x = set()
或
x = {1} # 必须有值，否则为dict

## 添加
x.add(value)


```python
x = {1,2,3,4}
y = {3,4,5,6,7}
```

## 交集
```python
ret = x & y
```
或
```python
ret = x.intersection(y)
```

