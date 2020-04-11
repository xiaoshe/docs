# swap
交换内容


## void swap(vector& x);
同类型vector交换内容
```cpp
vector<int> foo(3,100);
vector<int> bar(5,200);
foo.swap(bar);
// foo:[200 200 200 200 200]
// bar:[100 100 100]
```