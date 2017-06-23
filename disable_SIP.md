### 如何Disable SIP(System Integrity Protection )

1.重启Mac然后按住`Command + R` 键持续不放直到你听到系统启动的声音, 这个命令会让 OS X 进入 **Recovery Mode**。

2.当 OS X Utilities 屏幕出现的时候(**当你的系统版本osx EI Captain,你可以在Recovery Mode 看到Utilities屏幕显示出来, 但是对于系统版本为 MacOS Sierra的时候, 只会出现语言选项而看不到Utilities选项,你此时需要一个USB安装盘(有Macos) 插在mac上这时候就可以看到Utilities选项了!!**), 下拉屏幕顶部Utilities菜单并且选择Terminal。

3.输入如下命令并且按回车。 `csrutil disable; reboot`

* 如果你想enable SIP, 重启mac进入recovery mode并且打开Terminal输入以下命令: `csrutil enable; reboot`。

* 如果想了解SIP的状态可以再Terminal运行如下命令: `csrutil status`。

