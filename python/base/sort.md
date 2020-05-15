# 列表排序

### 1.内置方法sort()
list.sort(key=None, reverse=False)  
- key: 比较的元素，参数是列表的一个元素
- reverse: True降序，False升序（默认）
仅限python3, python3无cmp参数

```python
# 整数，默认
a = [2,1,3,5,4]
a.sort()
print(a)
>>> [1, 2, 3, 4, 5]

# 字符串，降序
b = ["a", "c", "b", "e", "d"]
b.sort(reverse=True)
print(b)
>>> ['e', 'd', 'c', 'b', 'a']

# 元组，默认按第一个元素排序
c = [(2,"c"), (1, "b"), (3, "a")]
c.sort()
print(c)
>>> [(1, 'b'), (2, 'c'), (3, 'a')]

# 元组，选择比较的元素
def cmp(e):
  return e[1]
c.sort(key=cmp)
print(c)
>>> [(3, 'a'), (1, 'b'), (2, 'c')]
# 等同于
c.sort(key=lambda x:x[1])


```
### 2.函数sorted()
