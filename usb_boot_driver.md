### 制作正式版 macOS 10.12 Sierra 安装 U盘启动盘
一、准备工作：

* 准备一个 8GB 或以上容量的 U 盘，确保里面的数据已经妥善备份好（该过程会抹掉 U 盘全部数据）

* 首先，在 Apple Store 下载 macOS 10.12 原版安装包。
或者通过其他途径下载双击打开，拖动.app 文件至自己的 应用程序（Applications）文件夹。

确定应用程序名字为「Install macOS Sierra.app」

二、格式化优盘
* 插入你的 U 盘，然后在`「应用程序」`->`「实用工具」`里面找到并打开`「磁盘工具」`
* 在左方列表中找到 U 盘的名称并点击
* 在分区信息中的 「名称」输入「ABCD」 (由于后面的命令中会用到此名称，如果你要修改成其他(英文)，请务必对应修改后面的命令)
* 在`「格式」`中选择 `「Mac OS 扩展 (日志式)」`
* 开始格式化


三、输入终端命令开始制作启动盘
* 请再次确保安装文件是保存在`「应用程序」`的目录中
* 在`「应用程序」`->`「实用工具」`里面找到`「终端」`并打开。也可以直接通过 Spotlight 搜索`「终端」`打开
* 复制下面的命令，并粘贴到「终端」里，按回车运行：
------命令开始------ 从sudo开始复制（不要复制这句话）

```
sudo /Applications/Install\ macOS\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/ABCD --applicationpath /Applications/Install\ macOS\ Sierra.app --nointeraction
```
------命令结束------ 到nointeraction结束（不要复制这句话）

命令说明：
`Install\ macOS\ Sierra.app` 这个是正式版的“安装 macOS Sierra” 正确位置
`ABCD `这个是优盘的名字


回车后，系统会提示你输入管理员密码，接下来就是等待系统开始制作启动盘了。这时，命令执行中你会陆续看到类似以下的信息：
 

（在这里需要输入密码）
```
Erasing Disk: 0%... 10%... 20%... 30%...100%...
Copying installer files to disk...
Copy complete.
Making disk bootable...
Copying boot files...
Copy complete.
Done.
```

当你看到最后有 `「Copy complete」`和`「Done」` 字样出现就是表示启动盘已经制作完成了！
 

四、U 盘启动安装 macOS Sierra 的方法


当你插入制作完成的 macOS Sierra U盘启动盘之后，桌面出现「Install macOS Sierra」的盘符那么就表示启动盘是正常的了。那么怎样通过 USB 启动进行全新的系统安装呢？


其实很简单，先在目标电脑上插上 U 盘，然后重启你的 Mac，然后一直按住「`option」(alt)` 按键不放，直到屏幕显示多出一个 USB 启动盘的选项。


这时选择 U 盘的图标回车，即可通过 U 盘来安装 macOS Sierra 了！这时，你可以直接覆盖安装系统(升级)，也可以在磁盘工具里面格式化抹掉整个硬盘，或者重新分区等实现全新的干净的安装。



