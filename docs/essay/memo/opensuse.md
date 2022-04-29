# Tumbleweed 配置小记

## 准备

下载 ISO 文件：

```
wget https://opentuna.cn/opensuse/tumbleweed/iso/openSUSE-Tumbleweed-DVD-x86_64-Current.iso
```

检查 ventoy 是否有可用[更新](https://www.ventoy.net/cn/doc_news.html)。

备份配置文件：

```
/etc/proxychains.conf
/etc/tlp.d
/etc/v2raya
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

- 需要删除的软件包：`ibus`、`fcitx`、`opensuse-welcome`、`kompare`、`discover`、`PackageKit`、`konversation`、`kmousetool`、`vlc`、`skanlite`
- 需要禁用的模组：`pattern:games`、`pattern:kde_pim`、`pattern:office`
- 需要安装的软件包：`git-core`、`flatpak`

重装时不必导入旧用户数据或新建普通账户。

## 初次启动

以 `root` 身份登陆系统。禁用全部的软件源：

```
zypper mr -da
```

添加第三方软件源并更新系统：

```
zypper ar -fcg https://opentuna.cn/opensuse/tumbleweed/repo/oss/ opentuna-oss
```
```
zypper ar -fcg https://opentuna.cn/opensuse/tumbleweed/repo/non-oss/ opentuna-non-oss
```
```
zypper ref && zypper dup -y
```

安装多媒体解码器：

```
zypper ar -cfp 90 https://mirrors.ustc.edu.cn/packman/suse/openSUSE_Tumbleweed/ packman
```
```
zypper refresh && zypper dist-upgrade --from packman --allow-vendor-change
```
```
zypper install --from packman ffmpeg gstreamer-plugins-{good,bad,ugly,libav} libavcodec-full
```

配置 Flatpak：

```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

将旧用户目录重命名：

```
mv /home/bh /home/bh.old
```

新建用户：

```
adduser bh
```
```
passwd bh
```
```
usermod -aG wheel $USER && usermod -aG libvirtd $USER
```

检查权限：

```
ls -lat /home/bh && id bh
```

矫正权限：

```
chown -R bh:bh /home/bh.old
```

需要重新装入的应用程序数据：

```
/home/bh.old/{公共,模板,文档,下载,视频,图片,音乐,Applications}
/home/bh.old/.fonts
/home/bh.old/.pip
/home/bh.old/.vscode
/home/bh.old/.bashrc
/home/bh.old/.gitconfig
/home/bh.old/.var
/home/bh.old/.r

/home/bh.old/.config/Code
/home/bh.old/.config/deadbeef
/home/bh.old/.config/fcitx
/home/bh.old/.config/fcitx5
/home/bh.old/.config/goldendict
/home/bh.old/.config/google-chrome
/home/bh.old/.config/icalingua
/home/bh.old/.config/kate
/home/bh.old/.config/keepassxc
/home/bh.old/.config/Kvantum
/home/bh.old/.config/obs-studio
/home/bh.old/.config/smplayer
/home/bh.old/.config/VirtualBox

/home/bh.old/.local/share/fcitx5
/home/bh.old/.local/share/konsole
/home/bh.old/.local/share/TelegramDesktop
```

## 以普通用户身份登陆系统

需要安装的软件列表：

|包名/名称|源|描述|子包/Flatpak 包名|
|---|---|---|---|
|`keepassxc`|发行版仓库|密码管理|
|`proxychains-ng`|发行版仓库|网络代理|
|`smplayer`|发行版仓库|多媒体播放器|`smplayer-themes`|
|`neofetch`|发行版仓库|概览信息输出工具|
|`telegram-desktop`|发行版仓库|即时通讯软件|
|`gimp`|发行版仓库|图片编辑|
|`filelight`|发行版仓库|磁盘/文件夹容量分析|
|`deadbeef`|发行版仓库|音乐播放器|
|`fcitx5`|发行版仓库|输入法|`fcitx5-configtool`、`fcitx5-chinese-addons`|
|`git-core`|发行版仓库|版本控制系统工具|
|`obs-studio`|发行版仓库|录屏|
|`gh`|发行版仓库|GitHub CLI|
|`opi`|发行版仓库|OBS 仓库助手|
|`wps-office`|OBS 仓库|文档办公|
|`flatpak`|发行版仓库|Flatpak 基础包|
|FreeFileSync|Flatpak Remote|文件同步/比对|`com.calibre_ebook.calibre`|
|Calibre|Flatpak Remote|电子书阅读器|`org.freefilesync.FreeFileSync`|
|Draw.io|Flatpak Remote|思维导图工具|`com.jgraph.drawio.desktop`|
|v2rayA|[GitHub](https://github.com/v2rayA/v2rayA/releases)|网络代理|`v2ray-core`|
|`virtualbox`|发行版仓库|虚拟机|
|`goldendict`|发行版仓库|字典|`goldendict-lang`|
|`google-chrome-stable`|Google|网络浏览器|
|`code`|Microsoft|源代码编辑器|
|Fluent Reader|Flatpak Remote|RSS 阅读器|`me.hyliu.fluentreader`|
|Icalingua++|[GitHub Appimage](https://github.com/Icalingua-plus-plus/Icalingua-plus-plus/releases)|即时通讯软件|
|Ventoy|[GitHub](https://github.com/ventoy/Ventoy/releases)|启动 U 盘刻录工具|
|Czkawka|Flatpak Remote|文件查重工具|`com.github.qarmin.czkawka`|
|`kvantum-manager`|发行版仓库|主题美化工具|`kvantum-manager-lang`|

```
sudo zypper in keepassxc proxychains-ng smplayer smplayer-themes neofetch telegram-desktop gimp filelight deadbeef fcitx5 obs-studio gh opi flatpak v2ray-core goldendict goldendict-lang fcitx5 fcitx5-configtool fcitx5-chinese-addons kvantum-manager kvantum-manager-lang gnome-keyring virtualbox
```
```
sudo usermod -aG vboxusers $USER
```
```
sudo reboot
```

安装相关的软件包：

```
flatpak install flathub com.calibre_ebook.calibre
```
```
flatpak install flathub org.freefilesync.FreeFileSync
```
```
flatpak install flathub com.jgraph.drawio.desktop
```
```
flatpak install flathub me.hyliu.fluentreader
```
```
flatpak install flathub com.github.qarmin.czkawka
```

安装 WPS：

```
sudo zypper addrepo https://download.opensuse.org/repositories/home:fusionfuture:office/openSUSE_Tumbleweed/home:fusionfuture:office.repo
```
```
sudo zypper refresh && sudo zypper install wps-office
```

安装并启用代理工具：

```
sudo rpm -i /home/bh/下载/packages/installer_redhat_*.rpm; sudo systemctl enable v2ray v2raya --now
```

使用 `gh` 登陆 GitHub 账户

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
sudo systemctl status power-profiles-daemon.service tlp.service
```
```
sudo systemctl mask power-profiles-daemon.service
```