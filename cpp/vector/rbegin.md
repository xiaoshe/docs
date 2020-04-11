# rbegin
反向迭代器开始


## reverse_iterator rbegin();
反向迭代器开始

## const_reverse_iterator rbegin() const;
反向迭代器开始
```cpp
vector<int> a;
a.push_back(1);
a.push_back(2);
a.push_back(3);
for (vector<int>::const_reverse_iterator it = a.rbegin(); it != a.rend(); ++it) {
  printf("%d ", *it); // 依次输出3 2 1
}
```