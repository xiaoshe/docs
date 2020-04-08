# reserve
重新分配空间
如果string大小已知，使用reserve申请足够空间，避免在字符串增长时多次申请空间

## void reserve(size_t n = 0);
重新分配内存