# Tumbleweed 配置小记（二）

其他配置文件

## Alias

在 `~/.bashrc` 中设置别名：

```shell
export PATH=$PATH:/home/bh/.local/bin
#将 Python 的可执行文件路径添加至 $APTH
export EDITOR=nano
#将默认文本编辑器指定为 nano

alias sudo="sudo "
#对 sudo 后的字符启用别名
alias zypper="proxychains4 zypper"
#对 zypper 使用代理
alias mkdocs="python3 -m mkdocs serve"
alias mkdocs-lh="cd /home/bh/文档/GitHub/THGLG/ ; python3 -m mkdocs serve"
alias mkdocs-wb="cd /home/bh/文档/GitHub/Whiteboard/ ; python3 -m mkdocs serve"
#更短的别名
alias pyc="proxychains4"
#更短的别名
alias tuna="wget https://opentuna.cn/opensuse/tumbleweed/iso/openSUSE-Tumbleweed-DVD-x86_64-Current.iso && wget https://opentuna.cn/opensuse/tumbleweed/iso/openSUSE-Tumbleweed-DVD-x86_64-Current.iso.sha256 "
#从 openTUNA 下载最新的 tumbleweed DVD 镜像
alias ustc="wget https://mirrors.ustc.edu.cn/opensuse/tumbleweed/iso/openSUSE-Tumbleweed-DVD-x86_64-Current.iso && wget https://mirrors.ustc.edu.cn/opensuse/tumbleweed/iso/openSUSE-Tumbleweed-DVD-x86_64-Current.iso.sha256 "
#从 USTC 下载最新的 tumbleweed DVD 镜像
alias flatpak="proxychains4 flatpak"
#对 flatpak 使用代理
alias nvidia="sudo prime-select nvidia"
#简化显卡切换命令
alias intel="sudo prime-select intel"
#简化显卡切换命令
alias clean="clear; exit"
#适用于 vscode 内置终端的退出命令
alias font-ref="fc-cache -fv"
#刷新字体
#alias pip-upgrade="pip freeze --user | cut -d'=' -f1 | xargs -n1 pip install -U"
#更新全部的 Python 包
alias ipp="ping opentuna.cn -c 6; ping baidu.com -c 6; ping 1.1.1.1 -c 6"
#测试网络连通性
alias yt-dlp="proxychains4 yt-dlp"
#为下载工具设置代理
alias sys-dup="sudo zypper ref; sudo zypper dup -y; flatpak update -y"
#更新整个系统
alias iftop="sudo iftop"
alias reboot="sudo reboot"
alias poweroff="sudo poweroff"
#为某些命令默认添加 sudo 权限
```

## git

配置 `git`

```
git config --global user.name "Hanjingxue Boling"
```
```
git config --global user.email bolingh@outlook.com
```
```
git config --global http.proxy http://127.0.0.1:20171
```

## proxychains-ng

配置代理工具：

```
sudo nano /etc/proxychains.conf
```
```shell
quiet_mode
#clash for windows
socks5  127.0.0.1 7890
#v2raya
#socks5  127.0.0.1 20170
```

## Python3

设置代理（`~/.config/pip/pip.conf`）：

```
[global]
proxy=http://localhost:7890
```

## TLP（可选）

```
cd /etc/tlp.d && ls
```

01-cpu.conf

```
CPU_SCALING_GOVERNOR_ON_AC=powersave
CPU_SCALING_GOVERNOR_ON_BAT=powersave

CPU_ENERGY_PERF_POLICY_ON_AC=balance_performance
CPU_ENERGY_PERF_POLICY_ON_BAT=power

CPU_BOOST_ON_AC=1
CPU_BOOST_ON_BAT=0

SCHED_POWERSAVE_ON_AC=0
SCHED_POWERSAVE_ON_BAT=1
```

02-usb.conf

```
USB_AUTOSUSPEND=1
```

03-battery.conf

```
START_CHARGE_THRESH_BAT0=50
# 开始充电阈值
STOP_CHARGE_THRESH_BAT0=80
# 停止充电阈值
```

## Cron（可选）

```shell
bh@c004-h0:~> crontab -l
0 2 * * *  /home/bh/Applications/qb-nox/qbittorrent-nox
```