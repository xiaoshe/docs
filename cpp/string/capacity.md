# capacity
返回已分配的存储的大小
假如当前capacity为n，
（1）如果追加字符数为m，则追加后新空间capacity为：如果m>=n，则为m+n；否则为n*2。此类函数有append，insert

## size_t capacity() const
返回已分配的存储的大小