## 字符串
字符串是一个总称, Rust 中有多种字符串

**分类**
- 字节序列
  - `str`: 字符串字面值, 但不能作为变量
  - `&str`: 实际使用的字符串:  字符串字面量 的引用, 不可变
  - `String`: 可以动态变化的常用字符串
  - `CStr`, `CString`: 兼容 C 语言的字符串
  - `OsStr`, `OsString`: 兼容不同平台的 unicode 标准
  - `Path`, `PathBuf`: 兼容不同平台的 文件路径
  - `&[u8]`, `Vec<u8>`: 数字化 字节序列
- 字符序列
  - `&[u32]`, `&[char]`: 不可变 字符序列
  - `Vec<u32>`, `Vec[char]`: 动态 字符序列
- 重点
  - 字节序列: `&str`, `String`
    - 用 1 到多个字节(u8)表示 1 个字符
    - 比较节省空间
    - 字符的坐标比较难确定
  - 字符序列: `&[char]`, `Vec[char]`
    - 用 1 个字符(u32), 表示一个字符
    - 占用空间较大
    - 一个字符一个坐标

- 区别
  ```rust, editable
  fn main() {
      let basic_str = "我爱 Rust";

      // 字节序列
      let byte_sque: String = basic_str
          .bytes()
          .map(|item| format!("{item:x}"))
          .collect::<Vec<String>>()
          .as_mut_slice()
          .join("_");

      // 字符序列
      let char_sque: String = basic_str
          .chars()
          .map(|item| format!("{:0<8x}", item as u32))
          .collect::<Vec<String>>()
          .as_mut_slice()
          .join("_");

      // 前3个字节表示 "我", 然后3个字节表示 "爱"
      // 最后5个字节依次对应" Rust" (空格也算)
      println!("字节序列 的数据排列方式: \n{byte_sque}");

      // 每个字符依次对应 "我爱 Rust"
      println!("字符序列 的数据排列方式: \n{char_sque}");
  }
  ```

**使用方法**
- 创建
  - 

// 按字节 (byte) 排列的串
let s: Vec<char> = String::from("love: ❤️");
let s2: &[u8; 2] = b"hi";

// 按字符 (char) 排列的串
let v: Vec<char> = s.chars().collect();

// 原始字符串
let a = r"abc";
let b = r#"abcd"#;
let c = r##"abcde"##;
let d = r###"abcdef"###;



// rust 中
// &str 和 String 应称为 字节序列, 以及字节迭代器 Bytes
// &[u8; 长度], Vec<char> 为 字符序列

