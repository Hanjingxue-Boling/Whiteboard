# openSUSE Tumbleweed

## 准备

下载 ISO 文件：

```
wget https://opentuna.cn/opensuse/tumbleweed/iso/openSUSE-Tumbleweed-DVD-x86_64-Current.iso
```

检查 ventoy 是否有可用[更新](https://www.ventoy.net/cn/doc_news.html)。

备份配置文件：

```
/etc/proxychains.conf
/etc/tlp.d/*
```

## 安装系统

禁止联网

|分区|大小|格式|备注|
|---|---|---|---|
|/boot/efi|512MB|efi|挂载，格式化|
|SWAP|8GB|swap|挂载，格式化|
|/|50GB|btrfs|格式化，并勾选启用系统快照。|
|/home|-|xfs|仅挂载|
|/bt|-|xfs|bt 做种文件存储分区|

- 需要删除的软件包：`ibus`、`fcitx`、`opensuse-welcome`、`kompare`、`discover`、`PackageKit`、`konversation`、`kmousetool`
- 需要禁用的模组：`pattern:games`、`pattern:kde_pim`、`pattern:office`
- 需要安装的软件包：`git-core`

重装时不必导入旧用户数据或新建普通账户。

## 初次启动

以 `root` 身份登陆系统

禁用全部的软件源：

```
zypper mr -da
```

添加第三方软件源并更新系统：

```
sudo zypper ar -fcg https://opentuna.cn/opensuse/tumbleweed/repo/oss/ opentuna-oss
```
```
sudo zypper ar -fcg https://opentuna.cn/opensuse/tumbleweed/repo/non-oss/ opentuna-non-oss
```
```
zypper ref && zypper dup -y
```

安装解码器：

```
zypper ar -cfp 90 https://mirrors.ustc.edu.cn/packman/suse/openSUSE_Tumbleweed/ packman
```
```
zypper refresh && zypper dist-upgrade --from packman --allow-vendor-change
```
```
zypper install --from packman ffmpeg gstreamer-plugins-{good,bad,ugly,libav} libavcodec-full
```

将旧用户目录重命名：

```
mv /home/bh /home/bh.old
```

使用 `yast` 添加新用户，并将新用户添加至 `wheel` 与 `libvirt` 用户组。

移动应用程序数据：

```
/home/bh.old/{桌面,文档,下载,视频,图片,音乐,Applications}
/home/bh.old/.fonts
/home/bh.old/.pip
/home/bh.old/.vscode
/home/bh.old/.config/Code
/home/bh.old/.config/deadbeef
/home/bh.old/.config/fcitx
/home/bh.old/.config/fcitx5
/home/bh.old/.config/fluent-reader
/home/bh.old/.config/google-chrome
/home/bh.old/.config/htop
/home/bh.old/.config/icalingua
/home/bh.old/.config/kate
/home/bh.old/.config/keepassxc
/home/bh.old/.config/minigalaxy
/home/bh.old/.config/obs-studio
/home/bh.old/.config/smplayer
/home/bh.old/.local/share/fcitx5
/home/bh.old/.local/share/konsole
/home/bh.old/.local/share/TelegramDesktop
/home/bh.old/.bashrc
/home/bh.old/.gitconfig
```

检查权限：

```
ls -lat /home/bh
```

矫正权限：

```
chown -R bh:users /home/bh
```

## 以普通用户身份登陆系统

安装软件：

```
sudo zypper in keepassxc proxychains-ng smplayer smplayer-themes neofetch htop FreeFileSync telegram-desktop gimp filelight deadbeef obs-studio minigalaxy gh opi
```

```
sudo zypper in fcitx5 fcitx5-configtool fcitx5-chinese-addons
```
```
sudo reboot
```

安装 WPS：

```
sudo zypper addrepo https://download.opensuse.org/repositories/home:fusionfuture:office/openSUSE_Tumbleweed/home:fusionfuture:office.repo
```
```
sudo zypper refresh && sudo zypper install wps-office
```

配置代理工具：

```
sudo nano /etc/proxychains.conf
-----
quiet_mode
socks5  127.0.0.1 7890
```

配置 `git`

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
$ git config --global http.proxy http://proxyserver.com:port
```

使用 `gh` 配置 `git`

```
gh auth status
```
```
gh auth login
```

安装 VScode

```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
```
```
sudo sh -c 'echo -e "[code]\nname=Visual Studio Code\nbaseurl=https://packages.microsoft.com/yumrepos/vscode\nenabled=1\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/vscode.repo'
```
```
sudo zypper ref && sudo zypper in code
```

安装谷歌 chrome：

```
sudo zypper ar http://dl.google.com/linux/chrome/rpm/stable/x86_64 google-chrome
```
```
wget https://dl.google.com/linux/linux_signing_key.pub
```
```
sudo rpm --import linux_signing_key.pub
```
```
sudo zypper ref && sudo zypper in google-chrome-stable
```

[美化 KDE](../../blog/eyecandy-kde.md)

启动 tlp:

```
sudo systemctl enable tlp --now
```
```
tlp-stat -s #依照提示，手动屏蔽相关内容
```
```
systemctl status power-profiles-daemon.service tlp.service
```
```
sudo systemctl mask power-profiles-daemon.service
```