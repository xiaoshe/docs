# cpp

## 常用容器
### string
- [string](https://github.com/xiaoshe/docs/blob/master/cpp/string-string.md): 构造函数
- [~string](https://github.com/xiaoshe/docs/blob/master/cpp/string-~string.md): 析构函数
- [append](https://github.com/xiaoshe/docs/blob/master/cpp/string-append.md): 当前值后面追加额外的字符
- assign: 指派新值，使用方法同构造
- at: 返回参数所指位置的字符的引用
- begin: 返回string的起始位置
- capacity: 返回已分配的存储的大小
- clear: 清除所有内容，使其变成一个空串
- compare: 比较字符串
- copy: 拷贝字符串到一数组
- c_str: 返回以null结尾的字符串指针
- data: 返回字符串指针
- empty: 返回是否为空
- end: 返回past-the-end字符的迭代器
- erase: 删除部分字符串
- find: 字符串查找，返回首次找到的位置，如果没有找到则返回npos
- find_first_not_of: 查找不出现在指定参数中的第一个字符，返回其位置
- find_first_of: 查找指定参数中任意字符的第一次出现，返回其位置
- find_last_not_of: 查找不出现在指定参数中的最后一个字符，返回其位置
- find_last_of: 查找指定参数中任意字符的最后一次出现，返回其位置
- get_allocator: 返回该对象的内存分配器的拷贝（通常不用）
- insert: 插入字符串
- length: 返回字符串长度
- max_size: 返回可存放的最大字符串的长度
- operator+=: 追加字符串
- operator=: 指派新值
- operator[]: 返回参数所指位置字符的引用
- push_back: 末尾追加一个字符
- rbegin: 反向迭代器开始
- rend: 反向迭代器末尾
- replace: 替换字符串
- reserve: 重新分配空间
- resize: 重新定义对象大小
- rfind: 查找字符串最后出现的位置
- size: 返回字符串大小
- substr: 返回子串
- swap: 交换内容
- npos: 空，静态常量-1
### list
### vector
### map
### set
