# operator[]
返回参数所指位置元素的引用


## reference operator[](size_type n);
返回参数所指位置元素的引用，可修改该元素
```cpp
vector<int> a(3); // 初始化为3个0
a[1] = 2; // a: [0 2 0]
```

## const_reference operator[](size_type n) const;
返回参数所指位置元素的引用，不可修改该元素
```cpp
void F(const vector<int>& a) {
  a[1] = 2; // 错误
  int b = a[1]; // 正确
}
```