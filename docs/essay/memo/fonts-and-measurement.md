# 字体与计量单位

## 衬线字体

衬线体（英语：Serif），是一种有衬线的字体，又称为有衬线体、衬线字、曲线描边字，俗称白体字；而与之相对的，没有衬线的字体则被称为无衬线体。衬线是字形笔画的起始段与末端的装饰细节部分[^1]。

衬线体（即“白体”），中国大陆地区和港台的印刷界称之为宋体。另外，无衬线体（sans serif）在中文通常称为黑体。

### 思源字体

|名称|包名|
|---|---|
|[Source Han Sans 思源黑体](https://github.com/adobe-fonts/source-han-sans)|`adobe-sourcehansans-cn-fonts`|
|[Source Han Serif 思源宋体](https://github.com/adobe-fonts/source-han-serif)|`adobe-sourcehanserif-cn-fonts`|
|[Source Han Mono 思源等宽](https://github.com/adobe-fonts/source-han-mono)|-|
|[Source Code Pro](https://github.com/adobe-fonts/source-code-pro)|`adobe-sourcecodepro-fonts`|


## 计量单位

>本段摘选自 [计算机网络通讯的【系统性】扫盲——从“基本概念”到“OSI 模型”](https://program-think.blogspot.com/2021/03/Computer-Networks-Overview.html)

信道就是“传送信息的通道”。首先，信道可以从广义上分为“物理信道 ＆ 逻辑信道”。

“带宽”指的是：某个信道在单位时间内最大能传输多少比特的信息。

“比特率”或“字节率”很容易搞混淆。用英文表示的话——大写字母 B 表示【字节】；小写字母 b 表示【比特】。1Byte = 8bit

由于带宽的数字通常很大，要引入“K、M、G”之类的字母表示数量级，于是又引出一个很扯蛋的差异——“10 进制”与“2 进制”的差异。

- 【10 进制】的 K 表示 1000；M 表示 1000x1000（1 百万）
- 【2 进制】的 K 表示 1024（2 的 10 次方）；M 表示 1024x1024（2 的 20 次方）

为了避免扯皮，后来国际上约定了一个规矩：对【2进制】的数量级要加一个小写字母 i。比如说：Ki 表示 1024；Mi 表示 1024x1024 ...... 以此类推。

举例：

- 1Kbps 表示 “1000 比特每秒”
- 1KiBps 表示 “1024 字节每秒”


[^1]: [衬线体 - Wikipedia](https://zh.wikipedia.org/wiki/%E8%A1%AC%E7%BA%BF%E4%BD%93)