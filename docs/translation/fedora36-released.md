# Fedora 36 已正式发布

## 作品信息

- 原文：[Announcing Fedora Linux 36](https://fedoramagazine.org/announcing-fedora-36/)
- 作者：[Matthew Miller](https://fedoramagazine.org/author/mattdm/)
- 许可证：[CC-BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/)
- 译者：Hanjingxue Boling
- 日期：2022-05-10

----

## 正文

今天，我很高兴与大家分享成千上万的 Fedora 项目贡献者辛勤工作的成果：我们的最新版本 Fedora Linux 36 已经发布！

### 因社区而生，为社区服务

通常，当我写这些公告时，我会谈论发布中的一些重大技术变化。这一次，我想把重点放在使这些变化发生的社区上。Fedora 不仅仅是一群孤立地工作的人——我们是朋友。事实上，这是我们的四个[基本原则](https://docs.fedoraproject.org/en-US/project/)之一。

我们最新的 Fedora 朋友之一，Juan Carlos Araujo 在 [Fedora Discussion 讨论帖](https://discussion.fedoraproject.org/t/the-end-of-my-distro-hopping-days/38445)中说得很好：

>除了功能性、稳定性、特性、底层的工作方式以及前沿性之外，我认为成就或改变发行版的是那些无形的东西，比如文档和社区。Fedora 拥有着这一切……尤其是无形资产。

多年来，我们一直在努力使 Fedora 成为一个包容且热情的社区。我们希望成为一个有经验的贡献者和新人可以一起工作的地方。就像我们希望 Fedora Linux 成为一个对 Linux 长期用户和新手都有吸引力的发行版。

说到 Fedora Linux，让我们来看看这一次的一些亮点。与往常一样，在从以前的版本升级之前，您应该确保您的系统完全是最新的。尤其是这一次，因为我们在 F34/F35 更新中解决了一些非常重要的升级相关的错误。如果不首先应用这些更新，您的系统升级到 Fedora Linux 36 时可能会失败。

### 桌面环境

Fedora Workstation 专注于桌面，特别是面向想要 “一切都能完美运行” 的 Linux 操作系统体验的用户。像往常一样，Fedora Workstation 采用了最新的 GNOME 版本：GNOME 42。虽然它并没有*完全*提供生活、宇宙和一切的答案，但 [GNOME 42](https://release.gnome.org/42/) 带来了很多改进。许多应用程序已移植到 GTK 4 以改进样式和性能。GNOME 42 中有两个新的应用程序：Text Editor 和 Console。他们的名字很贴切，所以你可以猜到他们做了什么。Text Editor 是新的默认文本编辑器，并且 Console 现可从软件仓库安装。

如果您使用 NVIDIA 的专有图形驱动程序，您的桌面会话现在将默认使用 Wayland 协议。 这使您可以在使用现代桌面混合器时利用硬件加速。

当然，我们生产的不仅仅是工作站版本。[Fedora Spins](https://spins.fedoraproject.org/) 和 [Labs](https://labs.fedoraproject.org/) 针对各种受众和用例，包括提供计算神经科学工具的 Fedora Comp Neuro，以及提供轻量级桌面环境的 [Fedora LXQt](https://spins.fedoraproject.org/en/lxqt/) 等桌面环境。不要忘记我们的替代架构：[ARM AArch64、Power 和 S390x](https://alt.fedoraproject.org/alt/)。

### 系统管理增强

Fedora Linux 36 包含 Ansible 的最新版本。Ansible 5 将 “engine” 拆分为 `ansible-core` 和[集合包](https://koji.fedoraproject.org/koji/search?match=glob&type=package&terms=ansible-collection*)。这使维护更容易，并允许您只下载您需要的集合。详情请参阅 [Ansible 5 移植指南](https://docs.ansible.com/ansible/devel/porting_guides/porting_guide_5.html)以了解如何更新您的 playbook。

从 Fedora Server 36 开始，Cockpit 提供了一个用于配置和持续管理 NFS 和 Samba 共享的模块。这允许管理员通过用于配置其他服务器属性的 Cockpit Web 界面管理网络文件共享。

### 其他更新

无论您使用哪种 Fedora Linux 变体，您都将获得开源世界所提供的最新版本。Podman 4.0 将在 Fedora Linux 36 中首次全面发布。Podman 4.0 有大量的变化和全新的网络栈。 它还带来了向后不兼容的 API 变更，因此请仔细阅读[上游文档](https://podman.io/releases/2022/02/22/podman-release-v4.0.0.html)。

根据我们的 “[第一](https://docs.fedoraproject.org/en-US/project/#_first)” 基本原则，我们更新了关键的编程语言和系统库包，包括 Ruby 3.1、Golang 1.18 和 PHP 8.1。

我们很高兴您能试用新版本！ 请前往 [https://getfedora.org/](https://getfedora.org/) 并立即下载。或者，如果您已经在运行 Fedora Linux，请按照[简易升级说明](https://docs.fedoraproject.org/en-US/quick-docs/upgrading/)进行操作。有关 Fedora Linux 36 中新功能的更多信息，请参阅[发行说明](https://docs.fedoraproject.org/en-US/fedora/f36/release-notes/)。

### 万一出现问题……

如果您遇到问题，请访问我们的 [Ask Fedora](https://ask.fedoraproject.org/) 用户支持论坛。这里有包括[常见问题](https://ask.fedoraproject.org/tags/c/common-issues/141/f36)的类别。

### 感谢大家

感谢在这个发布周期中为 Fedora 项目做出贡献的人们。我们喜欢您加入 Fedora 社区。请务必在 5 月 13 日至 14 日参加我们的[虚拟发布派对](https://hopin.com/events/fedora-linux-36-release-party/registration)！