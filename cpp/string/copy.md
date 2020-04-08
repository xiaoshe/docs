# copy
拷贝字符串到一数组


## size_t copy(char* s, size_t len, size_t pos = 0) const
从pos开始拷贝len个字符到s指向的空间，返回拷贝字符数
```cpp
string s("1234");
char buf[10]; // 空间要够
size_t n = s.copy(buf, 3, 1);
buf[n] = 0; // buf="234"
```