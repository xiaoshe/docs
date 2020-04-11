# at
返回参数所指位置的元素的引用


## reference at(size_type n);
取得位置n的元素的引用，可修改此数据。函数会检查是否越界，越界则抛出out_of_range

## const_reference at(size_type n) const;
取得位置n的元素的引用，不可修改此数据。函数会检查是否越界，越界则抛出out_of_range