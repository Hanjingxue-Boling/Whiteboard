# 配置 Python3

配置软件源：

```
bh@localhost:~> cat ~/.pip/pip.conf
[global]
index-url = http://mirrors.aliyun.com/pypi/simple/
[install]
trusted-host=mirrors.aliyun.com
```

设置相关的别名：

```
alias pipp="pip -m --proxy-server=http://127.0.0.1:7890"
alias mkdocs="python3 -m mkdocs serve"
alias pyc="proxychains4"
```

安装后，需要将一些目录（python 模块的可执行文件目录）添加到 `$PATH` 中：

```
$ export PATH=~/.local/bin:$PATH
```