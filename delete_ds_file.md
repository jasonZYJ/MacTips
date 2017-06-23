### Mac教程：如何删除`.DS_Store`

`.DS_Store`文件重新生成非常令人困扰，我们可以用终端命令简单的处理掉。

在 Mac OS X 系统下，几乎绝大部分文件夹中都包含 .DS_Store隐藏文件，这里保存着针对这个目录的特殊信息和设置配置，例如查看方式、图标大小以及这个目录的一些附属元数据。

在 OS X 系统中，这些文件是默认隐藏起来的，但是当我们将这些文件转移共享到 Windows 系统的时候，它们就会变成可见状态，并且看起来非常像是一些垃圾文件; 或者我们用命令让Finder总是显示隐藏的文件的时候这个文件总是存在,删除亦会重新生成.

我们可以用终端命令简单的处理掉，并且防止 `.DS_Store` 文件的再生。

打开终端窗口，并输入删除命令删除所有`.DS_Store`文件：

```
sudo find / -name ".DS_Store" -depth -exec rm {} \;
```

按下回车键盘之后，终端会提示用户名和密码，直接输入密码再按回车即可。

删除后继续在终端输入：

```
defaults write com.apple.desktopservices DSDontWriteNetworkStores true
```

然后按下回车，就可以防止 `.DS_Store` 文件的再生了。

如果恢复之前的总是生成`.DS_Store` 文件,那么需要在终端输入:

```
defaults write com.apple.desktopservices DSDontWriteNetworkStores false
```
