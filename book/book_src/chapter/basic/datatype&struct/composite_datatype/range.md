# 区间 `Range`
**使用方式**
- **创建**
  - **首末元素**
    - 全加上: `a..b`
    - 只加一个: `a..`, `..b`
    - 都不加: `..`
  - **是否半开**
    - 左闭有开: `a..b` (包括上面所有例子)
    - 全闭合: `a..=b` (也可以类比上面的例子, 但没有 `a..=`)
- **访问**  
  - 数组切片: `&arr[..4]`, `&mut arr[0..=5]`
  - for 循环: `for i in 2..6 {println!("{i}");}`
```rust, editable
```

**类型注解**
- `a..b`: `Range<整数>`
- `a..`: `RangeFrom<整数>`
- `..b`: `RangeTo<整数>`
- `..`: `RangeFull<整数>`
- `a..=b`: `RangeInclusive<整数>`
- `..=b`: `RangeToInclusive<整数>`
```rust, editable
```