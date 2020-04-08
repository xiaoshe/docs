# resize
重新定义对象大小
当n小于string长度，则将string长度缩小为n。
当n大于string长度时，超出部分将被填充。如果指定了c，则填充c，否则填充空字符

## void resize(size_t n);
重置大小
```cpp
string s("123456");
s.resize(4); // 重置大小为4，s="1234"

string s1("123456");
s1.resize(10); // s1="123456\0\0\0\0"
```

## void resize(size_t n, char c);
重置大小，并以c填充
```cpp
string s("123456");
s.resize(10, '9'); // 重置大小为10并用'9'填充，s="1234569999"
```