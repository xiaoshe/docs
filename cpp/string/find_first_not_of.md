# find_first_not_of
查找不出现在指定参数中的第一个字符，返回其位置


## size_t find_first_not_of(const string& str, size_t pos = 0) const
从pos开始查找不出现在str中的字符
```cpp
string s("123123");
s.find_first_not_of("31"); // 返回1
s.find_first_not_of("312"); // 返回npos
```

## size_t find_first_not_of(const char* s, size_t pos = 0) const
从pos开始查找不出现在s中的字符

## size_t find_first_not_of(const char* s, size_t pos, size_t n) const
从pos开始查找不出现在s前n的字符
```cpp
string s("123123");
s.find_first_not_of("312", 0, 1); // 返回1，等价于s.find_first_not_of("3");
```

## size_t find_first_not_of(char c, size_t pos = 0) const
从pos开始查找不是字符c的字符