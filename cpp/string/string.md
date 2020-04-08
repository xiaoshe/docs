# string
构造函数


## string()
默认构造函数

## string(const string& str)
拷贝构造函数

## string(const string& str, size_t pos, size_t len = npos)
从str的pos开始拷贝len个字符（如果len为npos则直到结尾）
```cpp
string s1("12345");
string s2(s1, 1, 2); // size:2 capacity:2
string s3(s1, 1, 10); // size:4 capacity:4
string s4(s1, 1, string::npos); // size:4 capacity:4
```

## string(const char* s)
拷贝字符串指针s，直到'\0'结束

## string(const char* s, size_t n)
拷贝s的前n个字符
```cpp
const char *s1 = "123";
string s2(s1, 10); // size:10 capacity:10
```

## string(size_t n, char c)
填充n个c
```cpp
string s1(3, 'x'); // size:3 capacity:3 s1="xxx"
string s2(3, 42); // size:3 capacity:3 s2="***"
```

## template <class InputIterator> string(InputIterator first, InputIterator last)
相同顺序拷贝范围[first, last)内的字符