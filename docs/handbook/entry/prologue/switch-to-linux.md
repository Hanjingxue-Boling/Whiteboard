---
title: "切换到 Linux"
description: "切换到Linux之前应当了解的一些事项。"
lead: "在开始非凡的 GNU/Linux 之旅之前，您应当了解这些。"
---

## 什么是 Linux ？

Linux 是一种自由和开放源码的类 UNIX 操作系统。该操作系统的[内核](https://en.wikipedia.org/wiki/Kernel_(operating_system))由 [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds) 在1991年10月5日首次发布，在加上[用户空间](https://en.wikipedia.org/wiki/User_space_and_kernel_space)的应用程序之后，成为 Linux 操作系统。只要遵循 [GNU 通用公共许可证](https://en.wikipedia.org/wiki/GNU_General_Public_License)（GPL），任何个人和机构都可以自由地使用 Linux 的所有底层源代码，也可以自由地修改和再发布。大多数 Linux 系统还包括像提供 GUI 的 X Window 之类的程序。除了一部分专家之外，大多数人都是直接使用 Linux 发行版，而不是自己选择每一样组件或自行设置。

注意，严格意义上来说，Linux 狭义上指的是 [Linux Kernel](https://en.wikipedia.org/wiki/Linux_kernel)，因为操作系统中包含了许多用户图形接口和其他实用工具。如今 Linux 常用来指基于 Linux 的完整操作系统，内核则改以 Linux 内核称之。[^1]

## 什么是 Linux 发行版？

Linux 发行版（英语：Linux distribution，也被叫做 GNU/Linux 发行版），为一般用户预先集成好的 Linux 操作系统及各种应用软件。一般用户不需要重新编译，在直接安装之后，只需要小幅度更改设置就可以使用，通常以软件包管理系统来进行应用软件的管理。Linux 发行版通常包含了包括桌面环境、办公包、媒体播放器、数据库等应用软件。现在有超过 300 个 Linux 发行版（详见 Linux 发行版列表）。大部分都正处于活跃的开发中，不断地改进。

由于大多数软件包是自由软件和开源软件，所以 Linux 发行版的形式多种多样——从功能齐全的桌面系统以及服务器系统到小型系统（通常在嵌入式设备，或者启动软盘）。除了一些定制软件（如安装和配置工具），发行版通常只是将特定的应用软件安装在一堆函数库和内核上，以满足特定用户的需求。 [^2]

## 什么是 openSUSE？

## 为什么选择 Linux 作为桌面操作系统？

## 迁移前的准备

### 自我评价

在将你的日常事务迁移至 Linux 之前，最好仔细思考一下这样做是否合适，因为从一个生态迁移至另一个生态是一件需要消耗大量时间和精力的工作。

Linux 主要应用场景：

- 服务器：Linux 一直被用来作为服务器的操作系统，并且已经在该领域中占据重要地位。
- 大型机：Linux 在大型机上越来越受欢迎，部分原因是定价和开源模式。
- 超级计算机：Linux 作为超级计算机的操作系统也占主导地位。截至 2017 年 11 月，500 强名单上的所有超级计算机都运行某种变体的 Linux 。
- 嵌入式设备：Linux 的低成本、强大的定制功能以及良好的移植性能，使得 Linux 在嵌入式系统方面也得到广泛应用。

谁适合用 Linux：

- 计算机、通讯、安全专业及相关领域从业者；
- 需要架设服务器、使用和研究单片机等嵌入式设备的人；
- 希望能够有效利用老设备性能，而无需因现代商业操作系统的硬件要求问题而备受困扰的人；
- 有空闲时间，不介意反复折腾系统，乐于尝试不同系统的人；
- 喜欢配置和调整系统的方方面面以适配自己的工作的人；
- 寻求免费，合法（授权来源正当，合乎版权法规）的非 Windows 或 macOS 系统的人。

### 一些建议

从其他操作系统转到 Linux 桌面环境并非一蹴而就，这里是我们的一点建议：

1. 循序渐进：从[虚拟机](../installation/virtual-machine.md)开始体验 Linux 桌面环境不是个坏主意，双系统（在一台电脑上同时安装 Windows 与 Linux）也是一种解决方案。不要想着在几天之内掌握整个 Linux，某个红帽[^rh]工程师[有言](https://www.zhihu.com/question/53295083/answer/2304247674)：“所以说学习没有捷径，那些‘速成’的东西只是暂时的绕开了你‘终归绕不开’的问题而已。”并且 Linux 桌面也只是 Linux 宇宙中的一小部分。

2. 善于求助：与苹果砸牛顿脑袋的年代相比，21世纪的信息交流渠道方便了许多。您有数不清的途径可以求助。首先是软件附带的用户手册、文档，其次是搜索引擎，比如 Google 和百度。然后是求助于社区，比如各种 Linux 论坛与聊天群。

3. 尝试开源软件：你可以在 Windows 上尝试一些优秀的 Linux 软件（它们通常会有 Windows 版），了解这些软件可以让你更快将 Windows 下常用软件替换成 Linux 下的开源软件。如：  
    
    - [Firefox](https://www.mozilla.org/en-US/firefox/new/) 网页浏览器  
    - [Thunderbird](https://www.thunderbird.net/en-US/) 邮件客户端  
    - [Krita](https://krita.org/) 平面绘画软件  
    - [VLC](https://www.videolan.org/vlc/) 多媒体播放器  
    - [Blender](https://www.blender.org/) 多用途的建模软件  

4. 检查兼容性：Linux 支持绝大部分开源文件格式和大部分通用文件格式，了解一些常见的开放格式有助于你快速地将 Windows 上的文件转换为 Linux 上可读写的文件：  
    
    - 看看你已有的 Windows 程序，检查 “另存为” 或是 “导出” 有哪些格式可用。  
    - 检查 Linux 应用程序中的 “打开” 或 “以...打开” 或是 “导入” 对话框，看看是否发现有在 Windows 程式中可用的任何格式。  
    - 检查 Linux 应用程序中的 “保存” 或是 “另存为” 对话框，看看它是否可以存成 Windows 使用者了解的格式。  
    - 去学习或了解一些通用和开源文件格式，例如：[Markdown](https://www.markdown.xyz/)、[归档与压缩文件](https://wiki.archlinux.org/index.php/Archiving_and_compression)、[开放文档格式](https://baike.baidu.com/item/%E5%BC%80%E6%94%BE%E6%96%87%E6%A1%A3%E6%A0%BC%E5%BC%8F)。

5. 试用 Live 环境：很多 Linux 发行版都有提供 LiveCD 或 LiveDVD 镜像文件。除了在虚拟机中使用 Linux ，使用 LiveCD 在物理机上启动 Linux 也是一个不错的主意，它可以让你检查一下 Linux 与你的电脑硬件的兼容性如何（如果你的电脑具有不受开源驱动支持的计算机硬件，那你无法在 LiveCD 中直接使用该硬件设备），并单纯看看 Linux 究竟是怎么样的。从 LiveCD 启动的系统将比安装到硬盘的系统慢很多，你对 LiveCD 所作出的绝大部分更改都不会保存或生效（如在 LiveCD 中安装软件，下载文件），它们都会在系统重启后恢复原样。 

那么，您准备好了吗？如果您的回答是肯定的，请点击页面右下方的箭头继续阅览吧。

[^rh]: 红帽，即 RedHat 公司，最成功的商业化 Linux 公司之一。
[^1]: 本节源自：https://en.wikipedia.org/wiki/Linux
[^2]: 本节源自：https://en.wikipedia.org/wiki/Linux_distribution