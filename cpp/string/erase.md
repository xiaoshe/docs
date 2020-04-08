# erase
删除部分字符串


## string& erase(size_t pos = 0, size_t len = npos)
删除pos开始的len个字符，len为npos时表明删到结尾
```cpp
string s("12345678");
s.erase(1, 4); // size:4 capacity:8 s="1678"


```

## iterator erase(iterator p)
删除p指向的字符，并返回该位置
```cpp
string s("12345678");
string::iterator p1 = s.begin() + 1;
string::iterator p2 = s.erase(p1); // s="1345678" p2指向'3'
string::iterator p3 = s.erase(s.begin() + 6); // s="134567" p3指向end()

```

## iterator erase(iterator first, iterator last)
删除[first, end)区间内字符，返回first指向位置
```cpp
string s("12345678");
string::iterator p = s.erase(s.begin() + 1, s.begin() + 3); // s="145678" p指向'4'
```