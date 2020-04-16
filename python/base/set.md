# 集合操作

## 创建
x = set()
或
x = {1} # 必须有值，否则为dict

## 添加
x.add(value)


## 交集
```python
x = {1,2,3,4}
y = {3,4,5,6,7}

ret = x & y
# 或
ret = x.intersection(y)

# 输出ret:{3,4}
```

