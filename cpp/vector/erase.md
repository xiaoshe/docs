# erase
清除某数据


## iterator erase(iterator position);
清除指定元素
```cpp
v.erase(v.begin() + 1);
```

## iterator erase(iterator first, iterator last);
删除范围[first, last)内元素