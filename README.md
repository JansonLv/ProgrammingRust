# fork说明

## 生成ePub格式
原因有二：

1. 经常使用kindle阅读，原作者生成pdf导入进去字体非常小，阅读很累，因此将该文档转移到了mdbook

2. 都学习rust，mdbook用起来啊

转移步骤

- 将原有src的文件删除，md内的markdown文件复制过去
- 设置book.toml中的src为.，好处是不用调整img路径，直接使用
- 安装mdbook-epub `cargo install mdbook-epub`
- 在book.toml中增加一行[output.epub]


## Building with mdbook

This book is built with [mdbook](https://rust-lang.github.io/mdBook/). You can
install it by running `cargo install mdbook`.

If you want to build it locally you can run one of these two commands in the root
directory of the repository:

- `mdbook build`

  Builds static html pages as output and place them in the `/book` directory by
  default.

- `mdbook serve`

  Serves the book at `http://localhost:3000` (port is changeable, take a look at
  the terminal output to be sure) and reloads the browser when a change occurs.

## License

The content of this repository is licensed under **MPL-2.0**; see [LICENSE](./LICENSE).

# Programming Rust

本书为《Programming Rust - Fast, Safe Systems Development》第2版的个人中文翻译，仅供学习和交流使用，如有侵权请联系作者删除

## 以下为英文原版购买地址

* 电子版[购买地址](https://www.amazon.com/-/zh/dp-B0979PWD4Z/dp/B0979PWD4Z/ref=mt_other?_encoding=UTF8&me=&qid=)
* 印刷版[购买地址](https://www.amazon.com/-/zh/dp-1492052590/dp/1492052590/ref=mt_other?_encoding=UTF8&me=&qid=)

---

## 下载（pdf）

见[Nightly Build](https://github.com/MeouSker77/ProgrammingRust/releases/tag/v0.99)

---

## 目录（markdown）

- [前言](s'r'c/preface.md)
- [译者序](src/translator.md)
- [第一章 系统程序员的福音](src/ch01.md)
- [第二章 Rust概览](src/ch02.md)
- [第三章 基本类型](src/ch03.md)
- [第四章 所有权与move](src/ch04.md)
- [第五章 引用](src/ch05.md)
- [第六章 表达式](src/ch06.md)
- [第七章 错误处理](src/ch07.md)
- [第八章 crate与模块](src/ch08.md)
- [第九章 结构体](src/ch09.md)
- [第十章 枚举与模式](src/ch10.md)
- [第十一章 trait与泛型](src/ch11.md)
- [第十二章 运算符重载](src/ch12.md)
- [第十三章 实用trait](src/ch13.md)
- [第十四章 闭包](src/ch14.md)
- [第十五章 迭代器](src/ch15.md)
- [第十六章 集合](src/ch16.md)
- 第十七章 字符串与文本
- [第十八章 输入输出](src/ch18.md)
- [第十九章 并发](src/ch19.md)
- [第二十章 异步编程](src/ch20.md)
- [第二十一章 宏](src/ch21.md)
- [第二十二章 unsafe代码](src/ch22.md)
- [第二十三章 外部函数](src/ch23.md)

---

## 说明

- 第17章没有翻译。
- 翻译的过程中仅保留了原版的内容，并没有还原原版的格式，例如配色方案、标题格式、页眉页脚格式等都和原版不同。
- 如果发现错误，欢迎提出issue或PR。
- Github Action会每天自动从最新的代码编译pdf，并上传到release的Nightly Build标签里。
- 有些字体并不是所有系统上都有并且不方便传播，所以在github上编译的本书没有指定字体，你可以自己修改指定的字体，然后自己编译。
- md版是从pdf版直接转换+校对生成的，除了失去了文内链接之外，还可能有很多错误没有发现，因此还是更推荐pdf版。

---

## 编译（fork后已无效，请参考fork说明）

1. 安装`tectonic`
2. 安装`python`
3. 安装`Pygements`
    ```bash
    pip install Pygments
    ```
4. 如果`src/main.tex`中有`\includeonly{xxx}`这一行且未被注释掉（%后的内容是注释），请在编译之前删除这一行
5. 编译pdf文件
    ```bash
    cd src
    tectonic -Z shell-escape main.tex
    ```
6. 生成的`main.pdf`就是最后的pdf文件

- note: 安装`Pygements`之后必须确保pip安装的可执行文件在`PATH`中，即`pygmentize -V`必须能正常打印出版本信息
- note: 如果安装`tectonic`之后`tectonic`不在`PATH`中，请把第5步中的`tectonic`替换成完整的路径
- note: 如果所有步骤都正确操作仍编译失败，欢迎提issue
