# assign
重新赋值


## template <class InputIterator> void assign(InputIterator first, InputIterator last);
将范围[first, last)内数据覆盖原数据
```cpp
vector<int> a;
a.assign(5, 123); // a:123 123 123 123 123
vector<int> b;
b.assign(a.begin() + 1, a.end()); // b:123 123 123 123
```

## void assign(size_type n, const value_type& val);
用n个val覆盖原数据