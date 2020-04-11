# reserve
重新分配空间
当参数n大于当前capacity时，则重新分配新空间，否则什么都不做。
如果vector大小已知，使用reserve申请足够空间，避免在数组增长时多次申请空间

## void reserve (size_type n);
重新分配空间
```cpp
vector<int> a;
a.push_back(1);
a.push_back(2);
a.push_back(3);
printf("cap:%ld size:%ld\n", a.capacity(), a.size()); // cap:4 size:3
a.pop_back();
printf("cap:%ld size:%ld\n", a.capacity(), a.size()); // cap:4 size:2
a.reserve(8);
printf("cap:%ld size:%ld\n", a.capacity(), a.size()); // cap:8 size:2
a.reserve(1);
printf("cap:%ld size:%ld\n", a.capacity(), a.size()); // cap:8 size:2
```