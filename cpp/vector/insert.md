# insert
插入元素


## iterator insert(iterator position, const value_type& val);
postion位置上插入一个元素，后面元素后移一位，并返回position
```cpp
// 插入前a:1 2 3
vector<int>::iterator it = a.insert(a.begin()+1, 4); // 在位置1上插入元素4
// 插入后a:1 4 2 3，it指向a.begin()+1
```

## void insert(iterator position, size_type n, const value_type& val);
在position位置上插入n个元素
```cpp
// 插入前a:1 2 3
a.insert(a.begin()+1, 3, 4);// 在位置1上插入3个4
// 插入后a:1 4 4 4 2 3
```

## template <class InputIterator> void insert(iterator position, InputIterator first, InputIterator last);
在position位置上插入范围[first, last)指向的数据
```cpp
b.insert(b.begin(), a.begin() + 1, a.begin() + 3);
```