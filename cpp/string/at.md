# at
返回参数所指位置的字符的引用


## char& at(size_t pos)
返回pos位置处的字符引用，如果修改则会修改原string。函数会检查是否越界，越界则抛出std::out_of_range
```cpp
string s("1234");
s.at(0) = '8'; // 修改后s="8234"
```

## const char& at(size_t pos) const
返回pos位置处的字符引用，不能修改。函数会检查是否越界，越界则抛出std::out_of_range