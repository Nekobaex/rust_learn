# 配置
配置文件是根文件夹下的 `book.toml`

## [book]
这是关于您的书的常规信息:
- **title**: 书名
- **authors**: 本书的作者
- **description**: 这本书的描述
- **src**: `.md` 文件的目录, 默认为根目录下的的 `src` 文件夹, 其中包含 `SUMMARY.md` 等 `.md` 文件
- **language**: 本书的主要语言，会被加入到网页的属性中: `<html lang="en">`

```toml
[book]
title = "Example book"
authors = ["John Doe", "Jane Doe"]
description = "The example book covers examples."
src = "book_src"  
language = "en"
```

## [rust]
Rust 语言的选项，与运行测试和运行环境集成相关
- **edition**: 默认情况下用于代码片段的 Rust 版本

```toml
[rust]
edtion = "2021"
```

## [build]
这控制着书的构建过程
- **build-dir**: html 页面生成的目录, 默认为根目录下的的 `book` 文件夹
- **create-missing**: 默认为 `true`, 若 `SUMMARY.md` 中有缺失文件, 将会自动创建, 
    若为 `false`, 则会报错

```toml
[build]
build-dir = "book_target"
create-missing = true
```

## [preprocessor]
预渲染器, 用于拓展一些小功能

## [output]
输出渲染器, 一般用于输出文件的改变, 和 [preprocessor] 类似
- [output.html]
- [output.markdown] (默认禁用)
- 第三方 输出渲染器集合: [github 连接](https://github.com/rust-lang/mdBook/wiki/Third-party-plugins#backends)


### [output.html]
- 常用
  - **default-theme**: 默认主题, 默认为 **Light**
  - **preferred-dark-theme**: 默认的深色主题, 默认为 **Navy**
  - **mathjax-support**: 添加对 MathJax 的支持, 默认为false
  - **additional-css**: 如果您需要在不覆盖整个样式的情况下稍微更改书籍的外观，您可以指定一组样式表，这些样式表将在默认样式表之后加载，您可以在其中更改样式
  - **additional-js**: 如果您需要在不删除当前行为的情况下向书中添加一些行为，您可以指定一组 JavaScript 文件，这些文件将与默认文件一起加载
  - **git-repository-url**: 该书的 git 仓库的 url, 如果提供了图标链接，将在书的菜单栏中输出
  - **input-404**: 用于丢失文件的 Markdown 文件的名称, 相应的输出文件将相同，扩展名替换为 html, 默认为 404.md
  site-url: 将托管图书的网址, 这是确保 404 文件中的导航链接和 脚本/css 导入正常工作所必需的，即使在访问子目录中的 url 时也是如此, 默认为 / The url where the book will be hosted. This is required to ensure
  - **cname**: 将托管您的图书的 DNS 子域或顶级域, 根据 GitHub Pages 的要求，此字符串将写入站点根目录中名为 CNAME 的文件（请参阅管理 GitHub Pages 站点的自定义域）
  
- 不常用
  - **theme**: 自定义主题的目录, 默认为根目录下的的 `theme` 文件夹, mdbook 自带的主题不在其中
  - **curly-quotes**: 将直引号转换为卷引号，但出现在代码块和代码跨度中的引号除外, 默认为false
  - **edit-url-template**: 编辑 url 模板，当提供时显示“建议编辑”按钮，用于直接跳转到编辑当前查看的页面, 例如 GitHub 项目将此设置为 https://github.com/<owner>/<repo>/edit/master/{path} 或对于 Bitbucket 项目将其设置为 https://bitbucket.org/<owner>/ <repo>/src/master/{path}?mode=edit 其中 {path} 将替换为仓库中文件的完整路径
  - **git-repository-icon**: 用于 git 仓库链接的 FontAwesome 图标类, 默认为fa-github
  - **no-section-label**: mdBook 默认在目录列中添加节标签, 例如，“1.”、“2.1”, 将此选项设置为 true 以禁用这些标签, 默认为false

#### [output.html.print]
页面右上角有一个打印图标, 点击可以启用单页打印, 将所有页面放到一个页面中打印
- **enable**: 默认为 `true`, 是否启用单页打印功能
- **page-break**: 默认为 `true`, 是否在章节之间插入分页符

#### [output.html.fold]
控制左侧导航栏的折叠功能
- **enable**: 默认为 `true`, 是否启用折叠功能
- **level**: 默认为 `0`, 不折叠的层数, 从上至下

#### [output.html.playground]
Rust 示例代码块的选项
- **editable**: 默认为 `false`, 是否允许编辑代码块
- **copyable**: 默认为 `true`, 是否在代码块上显示 复制按钮
- **copy-js**: Copy JavaScript files for the editor to the output directory. Defaults to true
- **line-numbers**: Display line numbers on editable sections of code. Requires both editable
- **runnable**: Displays a run button for rust code snippets. Changing this to false will disable the run in playground feature globally. Defaults to true

#### [output.html.search]
内置文本搜索的选项
- **enable**: Enables the search feature. Defaults to true.
- **limit-results**: The maximum number of search results. Defaults to 30.
- **teaser-word-count**: The number of words used for a search result teaser. Defaults to 30.
- **use-boolean-and**: Define the logical link between multiple search words. If true, all search words must appear in each result. Defaults to false.
- **boost-title**: Boost factor for the search result score if a search word appears in the header. Defaults to 2.
- **boost-hierarchy**: Boost factor for the search result score if a search word appears in the hierarchy. The hierarchy contains all titles of the parent documents and all parent headings. Defaults to 1.
- **boost-paragraph**: Boost factor for the search result score if a search word appears in the text. Defaults to 1.
- **expand**: True if search should match longer results e.g. search micro should match microwave. Defaults to true.
- **heading-split-level**: Search results will link to a section of the document which contains the result. Documents are split into sections by headings this level or less. Defaults to 3. (### This is a level 3 heading)
- **copy-js**: Copy JavaScript files for the search implementation to the output directory. Defaults to true.

#### [output.html.redirect]
[点击前往](https://rust-lang.github.io/mdBook/format/configuration/renderers.html#outputhtmlredirect)

### [output.markdown]