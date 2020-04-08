# substr
返回子串


## string substr(size_t pos = 0, size_t len = npos) const;
返回pos开始的len个字符
```cpp
string s("123456");
string s1 = s.substr(1); // s1="23456"
string s2 = s.substr(1, 3); // s2="234"
```