# begin
返回数组起始位置


## iterator begin();
返回数组起始位置，可修改该元素
```cpp
vector<Doc>::iterator i = v.begin();
i->id = 2;
```

## const_iterator begin() const;
返回数组起始位置，不可修改该元素
```cpp
vector<Doc>::const_iterator j = v.begin();
```