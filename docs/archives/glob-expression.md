# Glob 语法及解析

## 1 glob 简介

glob 是用于匹配符合指定模式的文件集合的一种语言， 类似于正则表达式， 但更加简单。

**Update-09-22**: 前两天阮一峰老师更新了他的博客，内容讲的就是 Glob, 强烈推荐。

- [命令行通配符教程 - 阮一峰](http://www.ruanyifeng.com/blog/2018/09/bash-wildcards.html)

## 2 glob 语法

glob 的语法很简单：

|通配符|描述|例子|匹配|不匹配|
|---|---|---|---|---|
|`*`|匹配任意数量的任何字符，包括无|Law*|Law, Laws, Lawyer|GrokLaw, La, aw|
|`?`|匹配任何**单个**字符|?at|Cat, cat, Bat, bat|at|
|`[abc]`|匹配括号中给出的一个字符|[CB]at|Cat, Bat|cat, bat|
|`[a-z]`|匹配括号中给出的范围中的一个字符|Letter[0-9]|Letter0, Letter1 … Letter9|Letters, Letter, Letter10|
|`[!abc]`|匹配括号中未给出的一个字符|[!C]at|Bat, bat, cat|Cat|
|`[!a-z]`|匹配不在括号内给定范围内的一个字符|Letter[!3-5]|Letter1…|Letter3 … Letter5, Letterxx|

Update-2018-07-18: <del>使用 **/* 可以匹配当前目录树中的所有文件， 通过 **/*.py 匹配所有后缀名为 .py 的文件</del>

- [维基百科](https://en.wikipedia.org/wiki/Glob_(programming))

## 3 .gitignore

git 的 .gitignore 文件可以使用 glob 模式匹配， 另外还有一些规则：

- 所有空行或者以 # 开头的行都会被 Git 忽略
- 匹配模式可以以 / 开头防止递归
- 匹配模式可以以 / 结尾指定目录
- 要忽略指定模式以外的文件或目录，可以在模式前加上惊叹号 ! 取反

## 4 Python glob

Python 有进行 glob 匹配的标准库， 使用也很简单：

```python
# -*- coding: utf-8 -*-
import glob

# glob 只有两个函数， 功能差不多， 只不过一个返回列表， 一个返回迭代器

glob.glob('*.org')  # 返回所有后缀名为 .org 的文件

glob.iglob('*/')  # 返回匹配所有目录的迭代器
```

标准库 glob 在 Python2 和 Python3 中是相同的。

----

## 版权信息

- 原文：[Glob 语法及解析](https://rgb-24bit.github.io/blog/2018/glob.html)
- 作者：[rgb-24bit](https://github.com/rgb-24bit)
- 许可证：[知识共享署名-非商业性使用 4.0 国际许可协议](http://creativecommons.org/licenses/by-nc/4.0/)


