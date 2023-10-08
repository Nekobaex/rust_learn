# 字符: `char`
**类型**  
`char` 1 字符, 4 字节, 32 位 (底层是 `u32`),  
包含所有 unicode 字符, 且兼容 ascii  

**注意**
- char 表示字符, byte 表示字节
- 没有 byte 类型, 但有 byte 的概念, 有一个 `Bytes 迭代器`
- 
**示例**
```rust, editable
fn main(){
    let a: char = '😄';
    let b: u8   = b'A';
    let c       = '\n';

    println!("{a} as u32: {}", a as u32);
    println!("{b} as char: {}", b as char);
    println!("c: '{c}'");

}
```