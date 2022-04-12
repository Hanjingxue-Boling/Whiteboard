# 电子前线基金会 —— Chrome 用户请注意：Manifest V3 具有欺骗性和威胁性 

- 原文：[Chrome Users Beware: Manifest V3 is Deceitful and Threatening](https://www.eff.org/deeplinks/2021/12/chrome-users-beware-manifest-v3-deceitful-and-threatening)
- 作者：[The Electronic Frontier Foundation](https://www.eff.org/)
- 许可证：[CC-BY 3.0](https://creativecommons.org/licenses/by/3.0/us/)
- 译者：Hanjingxue Boling
- 日期：2021-12-11

----

Manifest V3 是谷歌浏览器即将成为网络浏览器扩展世界的决定性一揽子变化，其作者将其定义为 “朝着隐私、安全和性能方向迈出的一步”。但我们认为这些变化对用户来说是一笔不小的交易。自从 Manifest V3 宣布以来，[我们已经说过了，并且继续这样说](https://www.eff.org/am/deeplinks/2021/11/manifest-v3-open-web-politics-sheeps-clothing)，因为它的实施现在迫在眉睫。与之前的 [FLoC](https://www.eff.org/deeplinks/2021/03/googles-floc-terrible-idea) 和 [Privacy Sandbox](https://www.eff.org/deeplinks/2019/08/dont-play-googles-privacy-sandbox-1)（隐私沙盒）一样，Manifest V3 是 Google 控制着占主导地位的网络浏览器和最大的互联网广告网络之一的固有利益冲突的另一个例子。

Manifest V3，或简称 Mv3，对隐私保护工作完全有害。它将限制 Web 扩展的功能——尤其是那些旨在监视、修改和计算浏览器与您访问的网站的对话的扩展。在新规范下，像这样的扩展——比如一些用于隐私保护的跟踪器拦截器——将大大降低性能。谷歌限制这种访问的努力令人担忧，特别是考虑到[谷歌在前 100 万个网站中的 75% 安装了跟踪器](https://spreadprivacy.com/biggest-tracker-networks/)。

Mv3 能否在安全方面发挥很大作用也是值得怀疑的。Firefox 保持着最大的不基于 Chrome 的扩展市场，Mozilla 表示将采用 Mv3 以实现跨浏览器兼容性。然而，在 [2020 AdBlocker Dev Summit](https://www.youtube.com/watch?v=tpDFS-GUytg&t=416s) 上，Firefox 的扩展运营经理谈到了扩展安全审查过程：“对于恶意扩展，我们认为对于 Firefox 而言，它已经处于可管理的水平…因为扩展主要对抓取不良数据感兴趣，因此它们仍然可以使用当前未阻塞的 webRequest API 来做到这一点。” 简单来说，这意味着当恶意扩展程序潜入安全审查过程时，它通常只想观察您的浏览器与您访问的任何网站之间的会话。在数据已经被读取之后，恶意活动发生在别处。更彻底的审查流程可以提高安全性，但 Chrome 并未表示他们会这样做。相反，他们的解决方案是限制所有扩展的功能。

至于 Chrome 对 Mv3 的另一个理由——性能——[普林斯顿和芝加哥大学的研究人员 2020 年的一项研究表明](https://kevin.borgolte.me/files/pdf/www2020-privacy-extensions.pdf)，隐私扩展，正是那些将受到 Mv3 阻碍的扩展，实际上提高了浏览器的性能。

网络浏览器扩展的开发规范可能看似杂草丛生，但更广泛的影响应该对所有互联网公民都很重要：这是谷歌定义我们如何在线生活的又一步。 考虑到谷歌多年来一直是[世界上最大的广告公司](https://www.theguardian.com/media/2017/may/02/google-and-facebook-bring-in-one-fifth-of-global-ad-revenue)，这些新的限制是家长式的，令人毛骨悚然。

但不要只相信我们的话。 以下是技术专家、隐私倡导者和扩展开发人员的一些想法，他们和我们一样对 Manifest V3 感到担忧：

>“网络浏览器应该代表用户行事并尊重用户的利益。不幸的是，Chrome 现在有一个作为谷歌代理的跟踪记录，而不是一个用户代理。它是唯一一个默认情况下缺乏有意义的隐私保护的主要网络浏览器，促使用户将活动与 Google 帐户相关联，并实施侵入性的新广告功能。尽管学术研究表明无需更改，但 Google 的最新更改将破坏 Chrome 隐私扩展。这些对用户怀有敌意的决定都直接归因于谷歌的监控商业模式，并得益于其在桌面浏览器市场的主导地位。”

- Jonathan Mayer，普林斯顿大学

>“Manifest V3 将 Chrome 定位为软件生存和死亡的全能仲裁者，打破了为同样不同用户的合法偏好和价值观服务的多样化扩展的理想。2017 年，当[谷歌从 Chrome 商店中禁止 AdNauseam](https://adnauseam.io/free-adnauseam.html) 时，它草率地切断了数万用户积累的数据，并剥夺了他们用于反击在线分析和操纵的免费开源扩展程序。事后看来，AdNauseam 是煤矿中的金丝雀，因为 Mv3 现在准备将用户与成千上万甚至数百万人依赖的一系列宝贵的隐私工具（包括广告拦截器）隔绝。一个为了提高所有者利益而大受欢迎的浏览器有效地扼杀了创新的独立开发者，同时缩小了个人塑造其在线体验的选择。”

- Helen Nissenbaum 和 Daniel Howe（AdNauseam 和 TrackMeNot 的创造者）

>“Manifest V3 是对互联网隐私的不利退步。”

- [Ghostery](https://www.ghostery.com/blog/manifest-v3-the-ghostery-perspective) 公司博客

>“几乎所有你今天所知道的浏览器扩展都会受到某种影响：比较幸运的将 ‘只’ 遇到问题，有些会瘫痪，有些将不复存在。”

- Andrey Meshkov, [AdGuard](https://adguard.com/en/blog/manifestv3-timeline.html) 公司博客