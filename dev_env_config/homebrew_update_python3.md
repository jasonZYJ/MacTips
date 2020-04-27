#### Mac使用Homebrew更新Python3

**前提**
系统：macOS
当前Python版本： 2.7.10
使用工具：Homebrew、Fish shell


本文是基于 Homebrew 快速升级Python3，因为涉及到系统文件，所以不对系统自带的 Python 2.7 进行删除，只是替换。

1. 安装Homebrew
  官网地址https://brew.sh/

  运行命令 `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`

2. 安装Python3
运行

  `brew install python3`

3. 修改Fish shell的配置文件
  通过设置一个 Alias 即可设置 python 的默认版本为 3

* 打开Fish shell配置文件

  `vim ~/.config/fish/config.fish`

* 修改配置文件 (注意这个路径需要看下是否一样)
  `alias python="/usr/local/Cellar/python/3.7.3/bin/python3"`
* 运行命令
  `source ~/.config/fish/config.fish`

4. 运行 python --version 即可查看当前 python 版本
