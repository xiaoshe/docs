# assign
指派新值，使用方法同构造


## string& assign(const string& str)
拷贝str

## string& assign(const string& str, size_t subpos, size_t sublen)
从str的pos开始拷贝len个字符（如果len为npos则直到结尾）

## string& assign(const char* s)
拷贝字符串指针s，直到'\0'结束

## string& assign(const char* s, size_t n)
拷贝s的前n个字符

## string& assign(size_t n, char c)
填充n个c

## template <class InputIterator> string& assign(InputIterator first, InputIterator last)
相同顺序拷贝范围[first, last)内的字符