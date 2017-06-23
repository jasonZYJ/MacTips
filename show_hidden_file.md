### 显示隐藏的文件
  
默认情况下，在 Mac 下是不显示隐藏文件的，Finder 也未提供设置是否显示隐藏文件的选项，不像 Windows 下，有一个“文件夹选项“设置界面里可以控制，但这并不表示 Mac 下无法显示隐藏文件，

方法一:
我可以通过“终端”，用命令行设置这个选项，命令如下：

**显示：**
```
defaults write com.apple.finder AppleShowAllFiles -bool true
```
**隐藏：**
```
defaults write com.apple.finder AppleShowAllFiles -bool false
```


方法二：
 
首先，转到你要查看隐藏文件的文件夹
接着，`Command-F`,搜索该文件夹
点击右侧的“+”号，出现搜索控制选项，默认是`Kind(种类)`,点击下拉列表，选择`other(其他)`, 找到`File invisible(文件可见性)`选项，并对右边的方块打勾。
OK了，现在你可以在搜索控制选项中选择文件的`File Visibility(文件可见性)`状态了，点击选项中的`invisible(可见性)`即可显示隐藏文件