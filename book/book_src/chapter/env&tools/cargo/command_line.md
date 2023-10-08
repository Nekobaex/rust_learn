# 命令行

**`cargo --help` 原文翻译**:
```
Usage: cargo [+toolchain] [OPTIONS] [COMMAND]

Options:
  -V, --version             打印版本信息并退出
      --list                列出已安装的命令
      --explain <CODE>      运行 `rustc --explain CODE`
  -v, --verbose...          使用详细输出(-vv very verbose/build.rs output)
  -q, --quiet               不打印 Cargo 日志消息
      --color <WHEN>        颜色: auto, always, never
  -C <DIRECTORY>            在执行任何操作之前, 将目录更改为 DIRECTORY (nightly-only)
      --frozen              强制使用缓存和 Cargo.lock 中的配置信息
      --locked              强制使用 Cargo.lock 中的配置信息
      --offline             在不访问网络的情况下运行
      --config <KEY=VALUE>  覆盖一个配置
  -Z <FLAG>                 启用 Cargo 的不安全特性 (nightly-only), 使用 'cargo -Z help' 查看详细信息
  -h, --help                打印帮助信息

一些常见的 cargo 指令 (使用 --list 查看所有命令):
    build, b    编译当前的 package
    check, c    分析当前的 package 并报告错误，但不要生成目标文件
    clean       删除目标 target 目录
    doc, d      构建这个 package 及其依赖项的文档
    new         创建一个新的 cargo package
    init        在现有目录中创建一个新的 cargo package
    add         向清单文件(Cargo.toml)添加新的依赖项
    remove      从清单文件(Cargo.toml)中删除依赖项
    run, r      编译并运行二进制文件
    test, t     测试
    bench       运行基准测试
    update      更新 Cargo.lock 中列出的依赖项
    search      从 crates.io 搜索包
    publish     打包, 并将此包上传到 crates.io
    install     安装一个 Rust 二进制文件
    uninstall   卸载一个 Rust 二进制文件
```

## 常用部分
- **初始化**
  - `> cargo new [项目名] --bin`
  - `> cargo new [项目名] --lib`
- **构建**
  - `> cargo check`
  - `> cargo build`
  - `> cargo run`
- **测试**
  - `> cargo test`
- **生成文档**
  - `> cargo doc`

    

