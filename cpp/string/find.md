# find
字符串查找，返回首次找到的位置，如果没有找到则返回npos


## size_t find(const string& str, size_t pos = 0) const
从pos开始查找str

## size_t find(const char* s, size_t pos = 0) const
从pos开始查找s

## size_t find(const char* s, size_t pos, size_t n) const
从pos开始查找s的前n个字符

## size_t find(char c, size_t pos = 0) const
从pos开始查找字符c