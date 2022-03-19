# 计划停用 software.opensuse.org（社区会议）

## 作品信息

- 原文：[Planning decomission of software.opensuse.org (Community meeting)](https://lists.opensuse.org/archives/list/factory@lists.opensuse.org/thread/F6SU2X2XFWX4OGEWLP4WO3JBKVHIFC6X/)
    - 类型：[openSUSE 邮件列表归档](https://lists.opensuse.org/archives/)邮件
- 作者：[Lubos Kocman](https://lists.opensuse.org/archives/users/f589eca7c10f41cf87e330d017fe74de/)
- 许可证：未知
- 译者：Hanjingxue Boling
- 日期：2022 年 3 月 19 日

----

## 正文

openSUSE 的用户们，你们好！

今天社区会议[^1]的结果之一是我们需要停用当前的 software.opensuse.org[^2] 代码库，因为我们找不到志愿者来维护它，也找不到进一步开发它的办法。目前的代码库和它的部署是与 ruby25 联系在一起的，这使得对目前使用的 rubygems 进行安全修复几乎是不可能。

我们的社交平台（forums-o-o、discord 等）显示了许多不正确使用服务导致 Leap 系统部分迁移到 Tumbleweed 的情况，或者你最终使用了启用许多无效软件源的 Tumbleweed。如果不加照顾，这种情况不会很快得到改善。

在会议上，我们同意需要停用该服务，并且仍然需要提供允许人们搜索和安装不存在于他们已安装的系统的软件或功能，或搜索版本编号或 NEXT/开发项目的状态的服务。

已经有一场关于该服务的未来的头脑风暴[^3]，但目前没有太大进展。

我真的希望这能引发一些建设性的讨论，帮助我们开发一个替代当前服务的方案。正如会议记录中所建议的那样，我们可以利用即将到来的机会，例如 gsoc、outreachy、hackweek。我们不应该试图让这成为一场 ruby vs python vs node 的战斗，而是尝试找到一个可持续的解决方案来保持服务在未来十年内运行。

预先感谢你的参与。

PS：目前关于 software.opensuse.org 还没有具体的退役日期，但也不会等待太久。

[^1]: https://etherpad.opensuse.org/p/weeklymeeting20220317
[^2]: https://github.com/openSUSE/software-o-o
[^3]: https://etherpad.opensuse.org/p/softwareworkshop