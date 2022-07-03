# 在 openSUSE 上游玩 Minecraft

## 准备

首先，前往官网 [Hellow Minecraft Launcher（HMCL）](https://hmcl.huangyuhui.net/) 下载适用于 Linux 平台的 Jar 文件。

## 安装依赖

你需要先安装两个基本包：

```
sudo zypper in openjfx java-17-openjdk
```

然后在命令行启动启动器：

```
java -jar HMCL*.jar
```

## 集成至开始菜单

设置一个 start.sh 脚本

```
#!/bin/sh
cd /path_to_dir_of_minecraft
java -jar HMCL-*.jar
```

然后在 ~/.local/share/applications 下创建一个 desktop 文件：

```
[Desktop Entry]
Encoding=UTF-8
Value=1.0
Type=Application
Name=HMCL
GenericName=Hellow Minecraft Launcher
Comment=a Minecraft game launcher
Icon=/path_to_icons
Exec="/path_to_start.sh" ""
Categories=Game;
Path=/path_to_minecraft
```