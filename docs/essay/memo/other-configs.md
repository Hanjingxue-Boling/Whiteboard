# 其他配置文件

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
#alias pip-upgrade="pip freeze --user | cut -d'=' -f1 | xargs -n1 pip install -U"
#更新全部的 Python 包
alias ping="ping bing.com"
#测试网络连通性
alias yt-dlp="proxychains4 yt-dlp"
#为下载工具设置代理
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

配置软件源（`~/.pip/pip.conf`）：

```
[global]
index-url = http://mirrors.aliyun.com/pypi/simple/
[install]
trusted-host=mirrors.aliyun.com
```

安装后，需要将一些目录（python 模块的可执行文件目录）添加到 `$PATH` 中：

```
export PATH=~/.local/bin:$PATH
```

## TLP

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
bh@c004-h0:/et
```