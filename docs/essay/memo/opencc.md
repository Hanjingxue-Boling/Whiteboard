# 使用 OpenCC 进行简繁中文转换

>[开放中文转换](https://github.com/BYVoid/OpenCC)（OpenCC，开放中文转换）是一个开源项目，用于繁体中文、简体中文和日文汉字（Shinjitai）之间的转换。支持中国大陆、台湾和香港之间的字符级和短语级转换、字符变体转换和地区成语。这不是普通话和粤语等之间的翻译工具。

## 安装

在 Tumbleweed 上安装 OpenCC

```
sudo zypper in opencc -y
```

## 使用

示例：

```
bh@c004-h0:~> ls && cat 繁体中文.txt
繁体中文.txt  公共  模板  视频  图片  文档  下载  音乐  桌面  Applications  BT-Network
OpenCC 是一個開源項目，用於繁體中文、簡體中文和日文漢字（Shinjitai）之間的轉換。支持中國大陸、臺灣和香港之間的字符級和短語級轉換、字符變體轉換和地區成語。這不是普通話和粵語等之間的翻譯工具。
bh@c004-h0:~> opencc -i 繁体中文.txt -c t2s -o 简体中文.txt
bh@c004-h0:~> cat 简体中文.txt
OpenCC 是一个开源项目，用于繁体中文、简体中文和日文汉字（Shinjitai）之间的转换。支持中国大陆、台湾和香港之间的字符级和短语级转换、字符变体转换和地区成语。这不是普通话和粤语等之间的翻译工具。
```

在如上的示例中，我将繁体中文文本写入到名为 `繁体中文.txt` 的文件中，然后使用 opencc 读取该文件，并读取配置文件 `t2s` 进行转换，再输出一个名为 `简体中文.txt` 的文件。

### 配置文件

有关 opencc 可用的配置文件如下：

|名称|用途|
|---|---|
|`s2t.json`|简体到繁体|
|`t2s.json`|繁体到简体|
|`s2tw.json`|简体到台湾正体|
|`tw2s.json`|台湾正体到简体|
|`s2hk.json`|简体到香港繁体|
|`hk2s.json`|香港繁体到简体|
|`s2twp.json`|简体到繁体（台湾正体标准）并转换为台湾常用词汇|
|`tw2sp.json`|繁体（台湾正体标准）到简体并转换为中国大陆常用词汇|
|`t2tw.json`|繁体（OpenCC 标准）到台湾正体|
|`hk2t.json`|香港繁体到繁体（OpenCC 标准）|
|`t2hk.json`|繁体（OpenCC 标准）到香港繁体|
|`t2jp.json`|繁体（OpenCC 标准，旧字体）到日文新字体|
|`jp2t.json`|日文新字体到繁体（OpenCC 标准，旧字体）|
|`tw2t.json`|台湾正体到繁体（OpenCC 标准）|

### 帮助信息

```
bh@c004-h0:~> opencc --help

Open Chinese Convert (OpenCC) Command Line Tool
Author: Carbo Kuo <byvoid@byvoid.com>
Bug Report: http://github.com/BYVoid/OpenCC/issues

Usage: 

   opencc  [--noflush <bool>] [-i <file>] [-o <file>] [-c <file>] [--]
           [--version] [-h]

Options: 

   --noflush <bool>
     Disable flush for every line

   -i <file>,  --input <file>
     Read original text from <file>.

   -o <file>,  --output <file>
     Write converted text to <file>.

   -c <file>,  --config <file>
     Configuration file

   --,  --ignore_rest
     Ignores the rest of the labeled arguments following this flag.

   --version
     Displays version information and exits.

   -h,  --help
     Displays usage information and exits.


   Open Chinese Convert (OpenCC) Command Line Tool
```