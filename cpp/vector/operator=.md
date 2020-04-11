# operator=
赋值


## vector& operator=(const vector& x);
重新赋值
```cpp
vector<int> a;
a.push_back(1);
a.push_back(2);
a.push_back(3);
vector<int> b;
b = a; // b:1 2 3
```