# OpenBSD - 报告问题

## 报告已发行版本的问题

在报告已发布版本的错误/问题之前，请查看此清单：

1. 首先，检查[有关该版本的补丁和说明](https://www.openbsd.org/errata.html)。
2. 接下来，找出是否有更新的版本可用。
3. 最后，检查 [OpenBSD 版本之间的更改](https://www.openbsd.org/plus.html)。

如果看起来没有任何东西可以解决你的问题，那么请在提交错误报告之前熟悉 [sendbug(1)](https://man.openbsd.org/sendbug)。

## 报告 `-current` 版本的问题

如果你的问题出在 `-current` 源代码树而不是 `-release` 或 `-stable` 上，

1. 至少测试两次问题，并在几天之内更新源代码。
2. 不要报告源代码树编译问题，除非它们一直存在。它们几乎总是你造成的错误，或者当你遇到它们时我们正在处理它们。从事该项目的人员每天至少进行一次 [make build](https://www.openbsd.org/faq/faq5.html)，通常每天使用不同的架构进行数次的编译。
3. 请记住，[AnonCVS](https://www.openbsd.org/anoncvs.html) 服务器比实际工作的源代码树晚几个小时更新。
4. 检查 [OpenBSD 版本之间所做的更改](https://www.openbsd.org/plus.html)以查看问题是否已得到解决。
5. 我们在创建快照时非常谨慎。有时会犯错误，我们对此表示歉意。阅读或写信给邮件列表比发送错误报告更合适。

## 如何创建问题报告

**始终提供尽可能多的信息。**尝试找出确切的问题。给出关于如何重现问题的明确说明。尽量用尽可能准确和不混淆的术语来描述它，特别是如果它不容易复现的话。通过说“它崩溃”或“我在我构建的这个盒子上遇到奇怪的中断问题”来描述问题是没有帮助的。与其他人交流（在邮件列表或任何其他知识渊博的用户聚集的论坛上）以确认问题是新的并且最好是可重复的。请尝试确保它不是使用损坏或不受支持的硬件或使用不受支持的构建选项或软件造成的本地问题。

请不要开始修复需要大量工作的问题，直到你确定你了解这些问题，特别是在我们的发布期，我们必须不改变代码的主要部分。如果你要写大量的代码，请在邮件列表中提及，以确保没有其他人已经在处理这个问题（节省重复劳动）。

每个错误报告中都应包含以下项目：

1. 重现该问题所需的从启动开始的确切步骤序列。这应该是自成一体的；仅仅发送一个没有参数和其他数据的裸命令是不够的。如果一个错误需要一个特定的事件序列，请列出这些。我们鼓励你尽量减少你的例子的大小，但这并不是绝对必要的。如果这个错误是可重复的，我们也会发现它。

2. 你得到的输出。请不要只说它 "没有工作 "或 "失败"。如果有错误信息，请显示出来，即使你不了解它。如果 OpenBSD 因为某个错误而崩溃，请说明是哪一个。如果什么都没发生, 就说出来. 即使你的测试案例的结果是程序崩溃或其他明显的情况，在我们的测试中可能不会发生。最简单的是复制终端的输出，如果可能的话。</p>
   注意：如果出现致命错误，提供的错误消息可能不包含所有可用信息。 在这种情况下，还要查看系统日志文件中的输出，例如存储在 /var/log 中的输出。 此外，如果你正在处理具有自己的日志文件的应用程序，例如 httpd，请检查其保存日志的位置是否存在错误。

3. OpenBSD 内核输出。 你可以使用 dmesg 命令获取此信息，但你的 dmesg 输出可能不包含 `/var/run/dmesg.boot` 中捕获的所有信息。如果是这种情况，请包括两者的信息。**请将此包含在所有错误报告中。**

4. 如果你运行与你的错误有关的第三方软件，请说明，包括什么版本。如果你在谈论快照，请提及，包括其日期和时间。

5. 内核崩溃（kernel panic）的回溯。如果你的内核出现崩溃并且你处于 [ddb(4)](https://man.openbsd.org/ddb) 提示符下，请按照建议在错误报告中提供崩溃消息以及 `trace` 和 `ps` 命令的输出。如果机器挂起，请尝试在挂起之前启用 `sysctl ddb.console=1` 并通过键盘上的 Ctl+Alt+Esc 进入 DDB（必须在 X 之外），或者如果使用串行控制台则发送 BREAK。如果由于某种原因，崩溃消息不可见，你可以使用 `show panic` 命令再次获取它。只要有可能，这是必不可少的。**没有崩溃消息、回溯和 ps 输出的崩溃报告是无用的。**`show registers` 的输出也可能很有价值。然后，你可能需要使用 `boot dump` 重新启动，以便 [savecore(8)](https://man.openbsd.org/savecore) 可以保存内核映像以进行进一步的事后调试，如 [crash(8)](https://man.openbsd.org/crash) 手册页中所述。

6. 如果你在使用 X.Org 服务器的架构上报告 X 窗口的问题，请在报告中包含完整的 `/var/log/Xorg.0.log` 文件以及 `dmesg.boot` 信息。

如果你的错误报告变得相当长，请不要害怕。那是生活中的一个事实。与其让我们从你那里榨取事实，不如第一次就报告一切。另一方面，如果你的输入文件很大，你可以先问问是否有人有兴趣研究它。

## 发送错误报告

如果可能，请使用 [sendbug(1)](https://man.openbsd.org/sendbug) 命令帮助生成错误报告。它将自动包含一些有关你的硬件的有用信息，这些信息有助于诊断许多问题。 此工具要求你的系统可以正确发送电子邮件。如果你无法在功能正常的 OpenBSD 机器上使用 `sendbug`，请将你的错误报告发送至 [bugs@openbsd.org](mailto:bugs@openbsd.org)。

也许你发来的是一个功能请求，不一定是一个错误。新功能是可以接受的，尤其是实现你建议的新功能的代码。

为了调试一些问题，我们必须有有问题的硬件。请记住，OpenBSD 项目的资源是有限的。 你可以[捐赠一些硬件](https://www.openbsd.org/want.html)。