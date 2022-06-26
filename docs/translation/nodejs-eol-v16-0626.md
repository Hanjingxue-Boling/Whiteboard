# 将 Node.js 16 的生命周期结束日期提前

## 译文信息

- 原文：[Bringing forward the End-of-Life Date for Node.js 16](https://nodejs.org/en/blog/announcements/nodejs16-eol/)
- 作者：Richard Lau
- 许可信息：© OpenJS Foundation. All Rights Reserved. Portions of this site originally © Joyent.
- 译者：Hanjingxue Boling
- 日期：2022-06-26

----

## 将 Node.js 16 的生命周期终止日期更改为 2023 年 9 月 11 日

### 总结

我们将 Node.js 16 的生命周期终止日期（EOL）提前了 7 个月，以与 2023 年 9 月 11 日结束对 OpenSSL 1.1.1 的支持相吻合。

### 为何如此？

当我们开发 Node.js 16 时，希望我们能够支持 OpenSSL 3。不幸的是，发布的时间不允许这样做，我们发布了带有 OpenSSL 1.1.1 的 Node.js 16。OpenSSL 1.1.1 [计划支持到 2023 年 9 月 11 日](https://www.openssl.org/policies/releasestrat.html)，比 Node.js 16 计划的生命周期结束日期（2024 年 4 月）提前了七个月。

我们评估了以下方案：

1. 什么都不做。Node.js 16 将在其生命周期的最后七个月内面临 OpenSSL 1.1.1 中的任何漏洞的风险。
1. 在 2023 年 9 月上旬结束对 Node.js 16 的支持，以与 OpenSSL 1.1.1 的 EOL 时间相契合。在此之前，我们有这么做的先例：我们[提前四个月结束对 Node.js 8 的支持](https://github.com/nodejs/Release/issues/186)时，当时恰逢 OpenSSL 1.0.2 的 EOL。
1. 根据针对 Node.js 17 和（采用 OpenSSL 3 的）18 报告的问题以及需要对我们的测试套件进行的调整，我们认为这一尝试是有风险的，并可能对一些应用程序造成兼容性问题。
1. 尝试使用[来自 CentOS Stream 8 的 OpenSSL 1.1.1](https://git.centos.org/rpms/openssl/tree/c8s) 替换原有的 OpenSSL 1.1.1。CentOS Stream 8 是 Red Hat Enterprise Linux 8 (RHEL 8) 的上游版本，其 openssl 软件包将在 RHEL 8 的产品生命周期内得到维护支持（[直到 2024 年 5 月 31 日](https://access.redhat.com/support/policy/updates/errata/)）。不幸的是，发行版维护者对 CentOS Stream 8 的 OpenSSL 所做的更改导致了一些差异（例如，[删除了几种算法](https://git.centos.org/rpms/openssl/blob/c8s/f/SOURCES/hobble-openssl)），这将导致某些应用程序出现兼容性问题。

经过考虑，我们决定风险最小的方案是避免切换已发布的 OpenSSL 版本可能带来的破坏性变化，并将 Node.js 16 的 EOL 提前到 2023 年 9 月 11 日，即 OpenSSL 1.1.1 支持终止的同一天。