# rfind
查找字符串最后出现的位置


## size_t rfind(const string& str, size_t pos = npos) const;
在pos前查找str最后出现位置
```cpp
string s("012341234");
size_t p = s.rfind("12", 4); // 位置4前查找"12"最后出现位置，p=1
```

## size_t rfind(const char* s, size_t pos = npos) const;
在pos前查找s指向字符串最后出现位置

## size_t rfind(const char* s, size_t pos, size_t n) const;
在pos前查找s前n字符最后出现位置
```cpp
string s("012341234");
size_t p = s.rfind("1211", 4, 2); // 在位置4前查找字符串"12"，p=1
```

## size_t rfind(char c, size_t pos = npos) const;
在pos前查找字符c最后出现位置