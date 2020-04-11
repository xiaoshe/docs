# vector
构造函数


## explicit vector(const allocator_type& alloc = allocator_type());
构造空数组

## explicit vector(size_type n, const value_type& val = value_type(), const allocator_type& alloc = allocator_type());
构造n个元素的数组，每个元素都是val的一个拷贝
```cpp
struct Doc {
  int    id;
  string name;
};
Doc d;
d.id = 1;
d.name = "abc";
vector<Doc> v(3, d); // v有3个元素，每个元素id=1,name="abc"

```

## template <class InputIterator> vector(InputIterator first, InputIterator last, const allocator_type& alloc = allocator_type());
将范围[first, last)内数据构造为一个数组
```cpp
vector<int> a(b.begin(), b.end()-1);
```

## vector(const vector& x);
拷贝构造函数