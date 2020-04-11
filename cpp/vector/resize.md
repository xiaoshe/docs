# resize
重新定义对象大小
当n小于vector长度，则将vector长度缩小为n。
当n大于vector长度时，超出部分将被填充。如果指定了val，则填充val，否则填充初始化值

## void resize(size_type n, value_type val = value_type());
重新定义对象大小
```cpp
vector<int> a;
a.push_back(1);
a.push_back(2);
a.push_back(3);
a.resize(2);
printf("cap:%ld size:%ld\n", a.capacity(), a.size()); // cap:4 size:2
a.resize(6, 1);
printf("cap:%ld size:%ld\n", a.capacity(), a.size()); // cap:6 size:6
// 此时数组a:[1 2 1 1 1 1]
```