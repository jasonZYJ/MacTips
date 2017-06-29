### Dock 栏只显示已打开的应用程序

默认情况下，Dock 栏不仅会显示用户设置为在 Dock 中保留的应用程序（不论打开与否）、系统项目（Finder 和废纸篓）以及堆栈，还会显示那些用户并未设置保留，却已经打开的应用程序的图标。

这种一个不漏的显示方式，虽然十分便于用户操作，但也容易变得讨人厌：

* 对那些已经有不少在 Dock 中保留的项目的用户来说，随着新增的应用图标和最小化窗口的挤占，Dock 栏会越变越小。这时，Dock 中不活跃的应用程序及堆栈就不仅让人分心，还影响操作效率。

* 对那些希望截取或录制屏幕内容的用户来说，为了保持内容的相关性，常常会在截取或录制之前将不需要的项目从 Dock 栏中移除，结束后再加以恢复，十分费力。
  
其实，在 OS X 中，我们只需要运行一小段命令，就可以让 Dock 只显示已打开应用，从而减少不必要的干扰。

**方法一**

在`终端`（你可以通过 Spotlight 或定位至`应用程序`-`实用工具`-`终端`找到它）中输入如下命令，回车确认即可：

```
defaults write com.apple.dock static-only -boolean true; killall Dock
```
待 Dock 重启后，你就会发现，现在在 Dock 栏中只显示已打开的应用程序了！

![](/images/display_active_apps_only_on_dock1.png)

如果你想恢复成默认设置，只需再次输入命令，并回车确认即可：

```
defaults write com.apple.dock static-only -bool FALSE; killall Dock
```

**方法二**

比起相对麻烦且容易出错的终端命令来说，利用 [OnyX](http://www.titanium.free.fr/) 这款免费的系统维护软件去设置，不仅更友好，恢复成默认的设置也更方便。

前往`参数`-`Dock`中，勾选`只显示已打开的应用程序`，并在弹出的警告窗口中点击`继续`重启 Dock 即可。

![](/images/display_active_apps_only_on_dock2.png)