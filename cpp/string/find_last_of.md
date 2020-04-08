# find_last_of
查找指定参数中任意字符的最后一次出现，返回其位置
与find_first_of类型，不同的是，本函数在指定pos时向前查找（其返回值小于等于pos）

## size_t find_last_of(const string& str, size_t pos = npos) const
从pos开始查找

## size_t find_last_of(const char* s, size_t pos = npos) const
从pos开始查找

## size_t find_last_of(const char* s, size_t pos, size_t n) const
从pos开始查找s前n字符中的任意字符

## size_t find_last_of(char c, size_t pos = npos) const
从pos开始向前查找字符c