# Windows 11 安装与调教

本文仅记录一些本人认为特别需要修改的地方。

## 获取镜像

在无法满足 Windows 11 的最低安装需求的情况（设备没有 TPM 2.0）下，前往[微软 Windows 11 下载页](https://www.microsoft.com/software-download/windows11)，选择一个合适的选项。然后下载 `Windows.iso`（使用安装助手的时候，只需要让 Windows 下载镜像文件即可，不必刻录到 U 盘）。

### 使用 Ventoy 刻录 U 盘

使用 [Ventoy](https://www.ventoy.net/cn/index.html) 将 U 盘或可移动设备转换为一个可启动的 Ventoy 设备。你只需要把 ISO/WIM/IMG/VHD(x)/EFI 等类型的文件直接拷贝到 U 盘里面就可以启动了，无需其他操作。

然后，启动 `VentoyPlugson.exe`，选择你刚刚作为启动 U 盘的设备，点击**启动**，然后你就会进入到 ventoy 的插件配置页面。在全局配置中，将 `VTOY_WIN11_BYPASS_CHECK` 设置为 1，这样启动时，就可以直接跳过 Windows 11 的安装检查。

最后，记得关闭插件的应用程序。

## 版本选择

个人推荐安装时选择 Windows 11 专业版。系统安装完成的初次启动时，不连接互联网可以设置本地账户（仅限专业版）；在最后一步，关闭全部的选项。

说什么改进体验，微软不过就是想收集你的隐私数据好卖给广告商罢了。ㄟ( ▔, ▔ )ㄏ

## 恢复 Windows 11 的鼠标右键菜单

要将 Windows 11 的鼠标右键菜单恢复成 Windows 10 的样式。

1. 按下 `Win + R` 快捷键，并输入 `regedit`。
2. 定位到 `HKEY_CURRENT_USER\SOFTWARE\CLASSES\CLSID`，找到 `{86ca1aa0-34aa-4e8b-a509-50c905bae2a2}`
3. 右键点击新创建的**项**，新建一个名为 `InprocServer32` 的项，按下回车键保存即可。保存后，退出重启 `explorer.exe` 即可。

## 使用 Dism++ 调整文件资源管理器

Dism++ 是微软 DISM 命令行工具的开源图形化前端，你可以在[此处](https://github.com/Chuyu-Team/Dism-Multi-language/releases)下载。在启动 Dism++ 后，点击左栏的**系统优化**，然后：  

1. 在**安全相关设置**中，将 UAC 调整为，*总是提醒我*；  
2. 在**开始菜单及 Windows 体验**中，将除了*登录界面默认打开小键盘*和*关闭 Onedrive* 以外的选项全部开启；注意每次编辑都需要重启一次 `explorer.exe`；  
3. 在 **Explorer** 中，打开**打开资源管理器时显示此电脑**、**创建快捷方式时不添加“快捷方式”文字**、**此电脑中视频、照片、文档、下载、音手、卓面、3D 对象七个文件夹**、**快速访问不显示常用文件夹**、**快速访问不显示最近使用的文件**  
4. 在**资源管理器导航窗口图标管理**中，打开**隐藏资源管理器导航窗口中的库**、**隐藏资源管理器导航窗口中的收藏夹**  

## Windows 更新与反病毒

Windows 更新会自动补齐基本的驱动和安全补丁，设备还有其他的驱动问题，请到设备生产厂商的售后网站下载相关驱动。虚拟机用户可以关闭 Windows 更新和反病毒程序，但对于实体机用户不建议这么做。

### 创建排除项

为了使得一些应用程序正常工作，你可以打开 Windows 安全中心，点击 *病毒和威胁防护->“病毒和威胁防护”设置->排除项*，在此处添加一些你会存放一些微软安全中心会认为是木马或病毒程序的东西的文件夹。

下载这些程序的时候，也直接把下载位置定向到此处，避免被微软安全中心直接干掉。

## Windows 设置

### 系统

- 储存：  
    建议打开**储存感知**，并设置自动运行存储感知。个人会将储存感知运行时间设置为 1 个月。
- 剪贴板：  
    建议打开**剪贴板历史记录**
- 通知：  
    取消勾选**提供关于如何设置设备的建议**和**使用 Windows 时获取提示和技巧**

### 个性化

- 锁屏界面：  
    取消勾选**在锁屏界面上获取花絮、提示、技巧等**
- 开始：  
    取消勾选**显示最近添加的应用**和**在“开始”、“跳转列表”和“文件资源管理器”中显示最近打开的项目**
- 任务栏：  
    关闭全部选项

### 辅助功能：  

在**键盘**中，关闭与粘滞键、过滤键和切换键相关的全部选项

### 隐私和安全性

- 在**常规**中，关闭全部选项
- 在**诊断和反馈**中，将反馈频率调成*从不*。

### Windows 更新：  
    
在**高级选项**中，关闭**传递优化**。

## 软件管理

### Geek Uninstaller

使用 [Geek Uninstaller](https://geekuninstaller.com/) 可以卸载一些微软为了打广告不让你卸载的东西，比如应该入土的 Edge 浏览器。

### 卸载 Edge 

**个人推荐卸载 Edge，并将默认浏览器替换为 chrome 或 firefox。**

因为我认为 Edge 是一个 chrome 拙劣的模仿者。整个产品即不如 chrome 简洁优雅，又想要和 Windows 深度绑定成为微软的新广告业务平台，然后时常打扰用户（官方还特意制作了一个充满广告和标题党的首页，并想要学习国产浏览器玩剩下的那一套）。开发者还想要贴合 edge 老用户的需求，而保留一些古怪的功能。

整个产品显得格局不够宽阔，唯一的优势就是同步不需要翻墙罢了。

### 微软商店

个人并不推荐使用微软商店安装 UWP 软件。UWP 就是个爹不疼（微软放其自生自灭）妈不爱（软件开发者不中意它）的东西。比较好用的 UWP 软件也就是 Windows 自带的截图、照片、TO-DO、天气和邮件。

### 基本运行库

为了正常使用 Windows 11，就需要安装一些基本的运行库：

- [DirectX 最终用户运行时 Web 安装程序](https://www.microsoft.com/zh-cn/download/details.aspx?id=35)
- [Microsoft Visual C++ 可再发行程序包最新支持的下载](https://docs.microsoft.com/zh-CN/cpp/windows/latest-supported-vc-redist?view=msvc-170)