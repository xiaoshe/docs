# replace
替换字符串


## string& replace(size_t pos,  size_t len,  const string& str);
str替换pos开始的len个字符
```cpp
string s("123456");
s.replace(1, 2, "abc"); // "abc"替换"23"，s="1abc456"
```

## string& replace(iterator i1, iterator i2, const string& str);
str替换迭代器[i1, i2)范围内字符
```cpp
string s("123456");
s.replace(s.begin() + 1, s.begin() + 3, "abc"); // "abc"替换"23"，s="1abc456"
```

## string& replace(size_t pos,  size_t len,  const string& str, size_t subpos, size_t sublen);
用str subpos开始的sublen个字符替换pos开始的len个字符
```cpp
string s("123456");
s.replace(1, 2, "abcdef", 1, 3); // "bcd"替换"23"，s="1bcd456"
```

## string& replace(size_t pos,  size_t len,  const char* s);
s指向字符串替换pos开始的len个字符

## string& replace(iterator i1, iterator i2, const char* s);
s指向字符串替换迭代器[i1, i2)范围内字符

## string& replace(size_t pos,  size_t len,  const char* s, size_t n);
s指向字符串前n个字符替换pos开始的len个字符
```cpp
string s("123456");
s.replace(1, 2, "abcdef", 3); // "abc"替换"23", s="1abc456"
```

## string& replace(iterator i1, iterator i2, const char* s, size_t n);
s指向字符串前n个字符替换迭代器[i1, i2)范围内字符

## string& replace(size_t pos,  size_t len,  size_t n, char c);
n个c替换pos开始的len个字符
```cpp
string s("123456");
s.replace(1, 2, 3, 'b'); // "bbb"替换"23", s="1bbb456"
```

## string& replace(iterator i1, iterator i2, size_t n, char c);
n个c替换替换迭代器[i1, i2)范围内字符

## template <class InputIterator> string& replace(iterator i1, iterator i2, InputIterator first, InputIterator last);
[first, last)替换[i1, i2)