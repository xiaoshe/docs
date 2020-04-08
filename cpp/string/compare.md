# compare
比较字符串
返回值：
0：相等
<0：第一个不相等字符小于参数，或所有字符相等但参数长度长
>0：第一个不相等字符大于参数，或所有字符相等但参数长度短

## int compare(const string& str) const
比较字符串

## int compare(size_t pos, size_t len, const string& str) const
从pos开始的len个字符与str比较

## int compare (size_t pos, size_t len, const string& str, size_t subpos, size_t sublen) const;
从pos开始的len个字符与str的subpos开始的sublen个字符比较

## int compare(const char* s) const
与一个字符串指针比较

## int compare(size_t pos, size_t len, const char* s) const
从pos开始的len个字符与s比较

## int compare(size_t pos, size_t len, const char* s, size_t n) const
从pos开始的len个字符与s指向的字符串前n个字符比较