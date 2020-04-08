# find_last_not_of
查找不出现在指定参数中的最后一个字符，返回其位置
与find_first_not_of类似，所不同的是，本函数指定pos后向前查找（其返回值小于等于pos）。若pos大于等于（含npos）字符串对象的长度，则意味着查找整个对象。

## size_t find_last_not_of(const string& str, size_t pos = npos) const
从pos开始查找

## size_t find_last_not_of(const char* s, size_t pos = npos) const
从pos开始查找

## size_t find_last_not_of(const char* s, size_t pos, size_t n) const
从pos开始查找不出现在s的前n个字符中的最后位置

## size_t find_last_not_of(char c, size_t pos = npos) const
从pos开始向前查找
```cpp
string s("123123");
s.find_last_not_of('1', 3); // 返回2，从[3]开始向前查找非'1'
```