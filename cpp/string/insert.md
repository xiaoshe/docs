# insert
插入字符串


## string& insert(size_t pos, const string& str)
在位置pos插入str
```cpp
string s1("abc");
string s2("1234");
s1.insert(1, s2); // size:7 capacity:7 s1="a1234bc"
```

## string& insert(size_t pos, const string& str, size_t subpos, size_t sublen)
在pos插入str的子串（从subpos开始的sublen个字符）

## string& insert(size_t pos, const char* s)
在位置pos插入s指向字符串

## string& insert(size_t pos, const char* s, size_t n)
在pos插入s前n个字符
```cpp
string s("abc");
s.insert(0, "123", 4); // s="123\0abc"，注意越界情况
```

## string& insert(size_t pos, size_t n, char c)
在pos插入n个字符c
```cpp
string s("abc");
s.insert(1, 2, '1'); // s="a11bc"
```

## void insert(iterator p, size_t n, char c)
在p指向位置插入n个c

## iterator insert(iterator p, char c);
在p指向位置插入字符c，并返回位置p

## template <class InputIterator> void insert(iterator p, InputIterator first, InputIterator last)
在p指向位置插入区间[first, last)