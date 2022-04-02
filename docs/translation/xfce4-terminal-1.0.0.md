# Xfce Terminal 1.0.0 稳定版已发布

## 作品信息

- 原文：[Xfce Terminal 1.0.0 stable release](http://users.uoa.gr/~sdi1800073/sources/xfce_blog12.html)
- 作者：[Anestis Kefalidis](http://users.uoa.gr/~sdi1800073/) 
- 许可证：未知
- 译者：Hanjingxue Boling
- 日期：2022-04-03

----

## 正文

经历 15 个月的不断改进后，新的 Xfce Terminal 稳定版本正式发布，配备了许多改进，以供大家享用！

### 新的维护者

从 2016 年开始直到 2020 年，Terminal 由 Igor Zakharov 管理。它在 2021 年停止维护了几个月，直到我在 9 月开始接手开发工作。这是 Terminal 的第一个由我担任维护者的稳定版本，我希望你会发现它对得起我的前辈和整个 Xfce 桌面环境设定的质量标准。

### 新的版本控制方案

在向 Xfce 社区询问了 Terminal 的版本控制方案并查看了它的历史后，我决定采用 Thunar 的旧版本控制方案。这意味着下一个开发版本周期将是 1.1.x，而下一个主要稳定版本将是 1.2.0。这将持续到我们发布 2.0.0 或发生一些重大变化（例如，移植到 GTK 4）。

### 改进

对于没有跟上 Terminal 发展历史的任何人，主要的改进如下所示：

- “滚动输出（Scrolling on ouput）”首选项已得到改进，如果你向上滚动，现在将暂时禁用。
- 现在支持覆盖滚动条。
- 你现在可以通过 UI 向前台进程发送信号。
- `--tab` 和 `--window` 命令行参数已经重新设计过，使之更加直观。
- 对于那些使用背景图像的人来说，“填充”是一种新的样式选项。
- “不安全粘贴”对话框已进行了重大改进，现在还为你提供了暂时禁用它的选项。
- 你现在可以更改右键单击的行为。
- 现在可以在运行时更改包含“Tab”键的加速器。
- 为 Xfce 应用程序创建了一个新的快捷方式编辑器，Xfce Terminal 是最早支持它的应用程序之一（需要 libxfce4ui 4.17.2 或更高版本）。
- 尽可能使用 XfceTitledDialog 以更好地与 Xfce 桌面的其余部分协同工作。

要更深入地了解所有新功能，你可以阅读我以前的博客（[0.9.0](http://users.uoa.gr/~sdi1800073/sources/xfce_blog07.html)、[0.9.1](http://users.uoa.gr/~sdi1800073/sources/xfce_blog09.html)、[0.9.2](http://users.uoa.gr/~sdi1800073/sources/xfce_blog11.html)）或代码存储库中的 [NEWS](https://gitlab.xfce.org/apps/xfce4-terminal/-/blob/master/NEWS) 文件。

### 底层设计

就底层改进而言，我大部分时间都在重写处理加速器和创建各种菜单的代码。我删除了 Xfce 终端中大部分已弃用的代码，并修复了旧代码中存在的各种小问题或不一致，同时还减少了代码库的大小。起初，这个过渡引入了一堆回归，但感谢社区中的测试人员，看起来它创建的任何快捷方式或 UI 问题都已得到修复。这种过渡的一个很好的好处是能够自定义 goto-tab 加速器。

我也确实花了一些时间修复构建警告并删除了 VTE 旧版本的代码。总而言之，我相信代码库比一年前更好，这将使我能够使 1.2.0 成为更大的版本。

### 未来的计划

#### Xfce Terminal

Xfce Terminal 的未来是光明的。我对 1.2.0 版本的一些目标是：

- 重写首选项对话框以使用 XfceTitledDialog 并将快捷方式编辑器集成到其中。
- 通过复用现有设置编辑器中的代码并使用它来消除隐藏的首选项，在 libxfce4ui 中创建一个新的设置编辑器小部件。
- 记录 Xfce Terminal 中的所有公开功能。
- 引入类似于 Profiles 的功能，它将关闭一堆未解决的问题。
- Xfce 环境之外的选项卡恢复。
- 改进 FreeBSD 支持情况

在我开始处理所有这些之前，我将处理此版本中报告的所有回归（我已经收到一个）。

#### 展示此版本中的功能和改进的视频：

<iframe width="560" height="315" src="https://www.youtube.com/embed/tVoAYXW-tbs" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/xuDRw-p5bCA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<iframe width="560" height="315" src="https://www.youtube.com/embed/jQsmE0k1LdM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>