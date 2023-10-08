# 向量 `Vec`
类似 js 里的数组, python 里的列表

**使用方式**
- **创建**
  - 默认方式: `Vec::new()` 创建一个 **空向量**
  - 使用 `vec![]` 宏
    - `vec![1, 2, 3]`
    - `vec!['m'; 64]`
- **访问** (和 array 一样)
  - 单个元素 `v[坐标]` 
  - 引用切片 `&v[Range<i32>]`
  - 借用切片 `&mut v[Range<i32>]`  

**常用方法和属性**
- **方法**
  - **栈** 
    - `.push(value)`
    - `.pop()`
    - `.len()`
    - `.is_empty()`
  - **迭代操作**
    - `.retain(FnMut)`
  - **其它元素操作** 
    - `.append(other_vec)`
    - `.clear()`
    - `.insert(index, value)`
    - `.resize(new_len, value)`
    - `.remove(index)`
    - `.swap_remove(index)`
  - **结构方法**
    - `::new()`


**注意**
- 长度可任意变化
- 只能有 1 个类型, 且固定不变, 可用 Option 实现存储多种类型
- 越界访问, 会 panic