### 让应用的`崩溃报告`不再烦人


在 OS X 中，如果某个应用程序突然崩溃了，将立即在屏幕的正中弹出崩溃报告（Crash Reporter）窗口，真是「简单又粗暴，横行又霸道」。对开发者或高阶 Mac 用户来说，通过崩溃报告，可以帮助其分析应用崩溃的原因等，但若频繁弹出的话，则不管是谁，都会受不了的

￼
如果你并不喜欢崩溃报告弹出的话，可以通过终端命令完全关闭崩溃报告窗口在桌面的显示，或者让其在「通知中心」中显示。

方法

* 关闭崩溃报告显示

如果你希望关闭崩溃报告窗口在桌面的显示，只需在「终端」中输入如下命令，回车确认即可。下次如果有应用程序崩溃或意外退出，崩溃报告将不再会在桌面中显示：
```
defaults write com.apple.CrashReporter DialogType none
```
恢复成默认的对话框形式的话，只需执行如下命令：
```
defaults write com.apple.CrashReporter DialogType crashreport
```
* 让崩溃报告在「通知中心」显示

如果你希望让崩溃报告在「通知中心」显示，只需在「终端」中输入如下命令，回车确认即可。下次如果有应用程序崩溃或意外退出，崩溃报告将以通知的形式显示在屏幕右上角：
```
defaults write com.apple.CrashReporter UseUNC 1
```
恢复成默认的对话框形式的话，只需执行如下命令：
```
defaults write com.apple.CrashReporter UseUNC 0
```
￼

说明

* 通常来说，最好让崩溃报告保持默认显示设置，因为发送崩溃报告给 Apple 或软件开发商能够帮助其调试和修正错误。但如果你并不喜欢的话，那就根据个人偏好修改默认设置好了
* 需要特别说明的是，不论是关闭崩溃报告在桌面的显示，还是令其在「通知中心」显示，都不会对崩溃报告本身造成任何影响。前述命令只不过是令其不再在用户界面显示，或让其换一种方式显示罢了。通过「控制台」或点击崩溃报告通知，我们依然能够正常查看到相关信息。 
￼

参考链接：
1. [OS X Daily: Disable the Crash Reporter Dialog in Mac OS X ](http://osxdaily.com/2010/02/15/disable-the-crash-reporter-dialog-in-mac-os-x/)
2. [OS X Daily: How to Make Crash Reporter Appear as a Notification in OS X ](http://osxdaily.com/2015/10/13/set-crash-reporter-as-notification-mac-os-x/)
3. [Youtube: Disable Crash Reporter or Make It A Notification](https://www.youtube.com/watch?v=Do2aC_YhGCU)
