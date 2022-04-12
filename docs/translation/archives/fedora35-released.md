# 值得等待：Fedora Linux 35 已发布！ 

- 原文：[Worth the wait: Fedora Linux 35 is here!](https://fedoramagazine.org/announcing-fedora-35/)
- 作者: [Matthew Miller](https://fedoramagazine.org/author/mattdm/)
- 许可证：CC-BY-SA 4.0
- 译者：Hanjingxue Boling
- 日期：2021-11-02

---- 

## 正文

今天，我很高兴与大家分享数千名 Fedora 项目贡献者的辛勤工作成果：我们的最新版本 Fedora Linux 35 来了！ 虽然我们打破了按计划发布六次发布的连续记录，但我们认为解决一些突出的阻塞错误更为重要。 Fedora 相信软件必须可用才能有用，所以虽然我们知道可预测的时间表很重要，但我们也确保每个版本都符合我们的[标准](http://fedoraproject.org/wiki/Fedora_35_Final_Release_Criteria)，无论时间表上怎么说。

### 适用于日用的 Fedora Linux

Fedora Editions 是面向桌面、服务器和云环境以及物联网中特定 “展示” 用途的目标输出。

Fedora Workstation 专注于桌面，尤其是面向那些希望获得 “开箱即用” 的 Linux 操作系统体验的软件开发者。这个版本的特点是 [GNOME 41](https://help.gnome.org/misc/release-notes/41.0/)，它建立在 GNOME 40（已在 Fedora Workstation 40 中发布）对桌面的重新构想上。GNOME 41 包括电源管理方面的改进。GNOME 软件在 GNOME 41 中也进行了大修，使其更容易浏览和发现应用程序。它还引入了 Connections，一个基于 VNC 和 RDP 的远程桌面的新客户端。

我们在此次发布中对 Fedora Cloud 进行了一些改进。 由于许多公共云提供商现在支持 UEFI 启动，因此云镜像具有混合启动支持，统一了传统（BIOS）和 UEFI 启动模式。 在将 BTRFS 更改为 Fedora Linux 33 中的默认文件系统之后，Fedora Cloud 35 现在使用 BTRFS 作为默认的文件系统。

当然，我们制作的不仅仅是这些版本。[Fedora Spins](https://spins.fedoraproject.org/) 和 [Labs](https://labs.fedoraproject.org/) 针对不同的受众和使用情况，包括为计算神经科学提供工具的 [Fedora Comp Neuro](https://labs.fedoraproject.org/en/comp-neuro/)，以及提供轻量级桌面环境的 [Fedora LXQt](https://spins.fedoraproject.org/en/lxqt/) 等桌面环境。Fedora Linux 35 的新变种是 [Fedora Kinoite](https://kinoite.fedoraproject.org/)：一个以 KDE Plasma 桌面为特色的可重置的桌面系统。而且，别忘了我们的备用架构。[ARM AArch64](https://alt.fedoraproject.org/alt/)、[Power 和 S390x](https://alt.fedoraproject.org/alt/)。

### 桌面改进

我们在 Fedora Linux 34 中把默认的音频系统换成了 PipeWire，现在我们通过添加新的 WirePlumber 会话管理器来改进这个系统。WirePlumber 允许对音频和视频的策略和规则进行更多的定制。它提供了更丰富的开发体验，并为大多数语言增加了绑定。

如果您启用了 Fedora Linux 桌面变体中的第三方软件源，这些软件源现在可以立即使用。此外，启用第三方软件源后，选定的 Flathub 应用程序可以通过过滤后的 Flathub 远程获得。这使访问一个精心策划的应用程序列表变得容易，这些应用程序不会给 Fedora 带来法律或其他问题，不会与 Fedora Flatpaks 重叠，而且运行得相当好。当然，你总是可以通过[添加远程](https://flatpak.org/setup/Fedora/)来获得 Flathub 中可用的全部应用程序。

### 其他更新

无论您使用的是 Fedora 的哪个变种，您都会得到开源世界的最新成果。在我们的 "[第一](https://docs.fedoraproject.org/en-US/project/#_first)"基础上，我们更新了关键的编程语言和系统库，包括 Python 3.10、Perl 5.34 和 PHP 8.0。Fedora Linux 35 还包括现代防火墙服务 [firewalld 的 1.0 版本](https://firewalld.org/2021/06/the-upcoming-1-0-0)。

我们很高兴你能尝试新的版本！现在就去 https://getfedora.org/ 1 下载它。或者如果您已经在运行 Fedora Linux，请遵循[简单的升级说明](https://docs.fedoraproject.org/en-US/quick-docs/upgrading/)。更多关于 Fedora Linux 35 的新功能的信息，请看[发行说明](https://docs.fedoraproject.org/en-US/fedora/f35/release-notes/)。

### 在万一出现问题的情况下…

如果您遇到了问题，请查看 [Fedora 35 常见错误页面](https://fedoraproject.org/wiki/Common_F35_bugs)，如果您有问题，请访问我们的 [Ask Fedora](https://ask.fedoraproject.org/) 用户支持平台。

### 谢谢所有人

感谢在这个发布周期中为 Fedora 项目做出贡献的数千人，特别是那些在大流行期间为使这个版本成为另一个了不起的版本而加倍努力工作的人。Fedora 是一个社区，很高兴看到我们互相支持的程度。请务必在 11 月 12 日至 13 日参加我们的[线上发布派对](https://hopin.com/events/fedora-linux-35-release-party/registration)！