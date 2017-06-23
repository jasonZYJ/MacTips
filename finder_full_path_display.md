#### Mac实用技巧——在Finder中显示文件完整路径


Finder默认是不显示路径的(顶部标题)，进入某个文件夹时只会显示当前文件夹的名字。

通过下面的命令可以在finder顶部的标题栏上显示完整路径。
在终端(Terminal)输入以下命令并回车：

```
defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES
```

把finder关了再打开,步骤:

**点击左上角的Logo - 强制退出 - 选择Finder - 重新开启 即可**

在标题栏中即可显示文件的完整路径，而且对着路径最左边的小图标点右键，就能快速访问路径中的任意一层。

当然了, 如果想要关掉这个功能的话,把 `YES` 改为 `NO` 即可
 
```
defaults write com.apple.finder _FXShowPosixPathInTitle -bool NO

```