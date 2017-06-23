### MAC OS X系统默认的截图路径是桌面文件夹，默认的截图格式是 PNG 图片格式，如何自定义设置呢？

* **截图保存路径**
打开终端（Terminal）并输入如下命令：

```
defaults write com.apple.screencapture location /path/ 
```
 (such as mine:  `/path/` 自定义为`/Users/J-Y/Downloads/`)
 
`/path/`即你想要设置的保存路径，比如将截图文件存储在用户目录的图片（Pictures）文件夹，命令则为：


```
defaults write com.apple.screencapture location ~/Pictures/
```

接下来，为了使得修改生效，输入下面这条命令：
`killall SystemUIServer`
当然，如果你习惯将截图保存在桌面的话，`/path/` 对应的路径为 `~/Desktop/`。

* **截图文件格式**

OS X 系统默认截图文件格式为 `png`，通过下面的终端（Terminal）命令可以修改截图文件格式为 `jpg` ：
```
defaults write com.apple.screencapture type jpg
```

另外，还可以将命令中的 `jpg` 修改为 `gif` 或 `pdf`，以及改回默认的 `png` 格式。同样别忘了输入上面那条使得修改生效的命令。

系统截图命令:

```
option + shift + 3  整个页面截图
option + shift + 4  选取界面截图
```