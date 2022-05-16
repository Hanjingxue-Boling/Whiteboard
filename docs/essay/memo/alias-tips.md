# alias 命令小记

在计算机中，`alias` 是各种命令行解释器（shell）中的一个命令，它可以用另一个字符串替换一个单词。它主要用于缩写系统命令，或为常用命令添加默认参数[^1]。`alias` 是一个非常实用的命令。

## 基本格式

你可以使用一个单词（`word`）作为一个很长的命令（`command`）的缩写，如下：

```
alias word="command"
alias mkdocs="python3 -m pip mkdocs server"
```

你可以直接运行 `$ alias` 列出所有的可用别名。

## 临时别名

在终端使用诸如 `$ alias word="command"` 之类的命令可以临时设置一个别名，但退出终端会话后，临时别名也会被丢弃。

## 永久设置别名

对于 Bash Shell，普通用户可将别名添加至 `$HOME/.bashrc` 文件。如：

```
bh@c004-h0:~> cat .bashrc
# Sample .bashrc for SUSE Linux
# Copyright (c) SUSE Software Solutions Germany GmbH

# There are 3 different types of shells in bash: the login shell, normal shell
# and interactive shell. Login shells read ~/.profile and interactive shells
# read ~/.bashrc; in our setup, /etc/profile sources ~/.bashrc - thus all
# settings made here will also take effect in a login shell.
#
# NOTE: It is recommended to make language settings in ~/.profile rather than
# here, since multilingual X sessions would not work properly if LANG is over-
# ridden in every subshell.

test -s ~/.alias && . ~/.alias || true
alias mkdocs="python3 -m mkdocs serve"
alias pyc="proxychains4"
alias tuna="wget https://opentuna.cn/opensuse/tumbleweed/iso/openSUSE-Tumbleweed-DVD-x86_64-Current.iso"
alias flatpak="pyc flatpak"
```

然后运行 source 命令使新配置生效：

```
source ~/.bashrc
```

要删除别名，可使用 `unalias` 命令：

```
unalias alias_name
```

## 设置全局别名

要为所有用户设置别名，可在 `/etc/profile.d` 下新建一个名为 `00-aliases.sh` 的 shell 脚本，然后将别名填入脚本中，如下[^2]：

```
bh@c004-h0:~> cat /etc/profile.d/00-aliases.sh
alias sudo="sudo "
alias zypper="proxychains4 zypper"
```

!!! attention
    并不建议直接编辑 `/etc/bash.bashrc` 文件来添加别名，以防止出现直接损坏系统配置文件的情况。

注意：

- `/etc/profile` 是在 `~/.profile` 之前运行的全局文件。
- `/etc/profile.d/` 是一个文件夹，其中包含 `/etc/profile` 调用的脚本
- 当 `/etc/profile` 被调用时（即你启动或登录 shell 时），它会在 `/etc/profile.d/` 中搜索任何以 `.sh` 结尾的文件，并使用以下命令之一运行它们：  
    ```
    source /etc/profile.d/myfile.sh
    ```
    ```
    . /etc/profile.d/myfile.sh
    ```
- 将文件名称以 `00` 开头，可以让 shell 首先执行该脚本。

### 处理使用 sudo 时不能使用 alias

同样地，在 `~/.bashrc` 或者 `/etc/profile.d/00-aliases.sh` 中添加：

```
alias sudo="sudo "
```

Bash 只检查命令的第一个单词是否有别名，之后的任何单词都不会检查。这意味着在像 sudo l 这样的命令中，bash 只检查第一个单词 (sudo) 的别名，忽略 l（`alias l="ls -alF"`）。你可以通过在别名值的末尾添加一个空格来告诉 bash 检查别名之后的下一个单词（即 sudo）[^3]。

[^1]: [alias (command) - Wikipedia](https://en.wikipedia.org/wiki/Alias_(command))
[^2]: [How can I preset aliases for all users?](https://askubuntu.com/questions/610052/how-can-i-preset-aliases-for-all-users)
[^3]: [Aliases not available when using sudo](https://askubuntu.com/questions/22037/aliases-not-available-when-using-sudo)