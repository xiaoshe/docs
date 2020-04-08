# find_first_of
查找指定参数中任意字符的第一次出现，返回其位置


## size_t find_first_of(const string& str, size_t pos = 0) const
从pos开始查找str中出现的任意字符
```cpp
string s("123123");
s.find_first_of("a23"); // 返回1(字符2所在位置)
s.find_first_of("a23", 2); // 返回2(字符3所在位置)
```

## size_t find_first_of(const char* s, size_t pos = 0) const;
从pos开始查找s指向的字符串中出现的任意字符

## size_t find_first_of(const char* s, size_t pos, size_t n) const
从pos开始查找s前n字符中的任意字符
```cpp
string s("123123");
s.find_first_of("a23", 2, 2); // 返回4('2'), 等价于s.find_first_of("a2", 2);
```

## size_t find_first_of(char c, size_t pos = 0) const
从pos开始查找字符c