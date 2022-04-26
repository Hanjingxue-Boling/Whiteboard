# 其他配置文件

!!! warning
    施工中……

## Alias

在 `~/.bashrc` 中设置别名：

```shell
alias sudo="sudo "
#对 sudo 后的字符启用别名
alias zypper="proxychains4 zypper"
#对 zypper 使用代理
alias mkdocs="python3 -m mkdocs serve"
#更短的别名
alias pyc="proxychains4"
#更短的别名
alias tuna="wget https://opentuna.cn/opensuse/tumbleweed/iso/openSUSE-Tumbleweed-DVD-x86_64-Current.iso"
#从 openTUNA 下载最新的 tumbleweed DVD 镜像
alias ustc="wget https://mirrors.ustc.edu.cn/opensuse/tumbleweed/iso/openSUSE-Tumbleweed-DVD-x86_64-Current.iso"
#从 USTC 下载最新的 tumbleweed DVD 镜像
alias flatpak="proxychains4 flatpak"
#对 flatpak 使用代理
alias nvidia="prime-select nvidia"
#简化显卡切换命令
alias intel="prime-select intel"
#简化显卡切换命令
alias clean="clear; exit"
#适用于 vscode 内置终端的退出命令
alias font-ref="fc-cache -fv"
#刷新字体
alias pip-upgrade="pip freeze --user | cut -d'=' -f1 | xargs -n1 pip install -U"
#更新全部的 Python 包
```

## git

## Python3

配置软件源（`~/.pip/pip.conf`）：

```
[global]
index-url = http://mirrors.aliyun.com/pypi/simple/
[install]
trusted-host=mirrors.aliyun.com
```

设置相关的别名（`~/.bashrc`）：

```
alias pipp="pip -m --proxy-server=http://127.0.0.1:7890"
alias mkdocs="python3 -m mkdocs serve"
alias pyc="proxychains4"
```

安装后，需要将一些目录（python 模块的可执行文件目录）添加到 `$PATH` 中：

```
$ export PATH=~/.local/bin:$PATH
```

