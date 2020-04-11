# front
返回第一个元素的引用
空数组上调用此函数将引起未定义行为

## reference front();
返回第一个元素的引用，可修改该元素
```cpp
Doc& d2 = v.front();
d2.id = 3;
```

## const_reference front() const;
返回第一个元素的引用，不可修改该元素