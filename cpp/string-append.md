# append
当前值后面追加额外的字符

## string& append(const string& str)
追加另一个string对象str

```cpp
string s1("123");
string s2("4567");
s1.append(s2); // size:7 capacity:7 s1="1234567"
```

## string& append(const string& str, size_t subpos, size_t sublen)
追加str的子串，从subpos开始的sublen个字符（如果str很短或sublen是npos，则直到结尾）

```cpp
string s1("123");
string s2("4567");
s1.append(s2, 2, 1); // size:4 capacity:6 s1="1236"
```

## string& append(const char* s)
追加字符串指针s，直到'\0'结束

## string& append(const char* s, size_t n)
追加字符串指针s前n个字符

## string& append(size_t n, char c)
追加n个字符c

## template string& append(InputIterator first, InputIterator last)
相同顺序追加范围[first, last)内的字符
