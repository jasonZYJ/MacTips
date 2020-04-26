### 如何在 macOS Catalina 中运行 64 位 KindleGen
 
如果你是 macOS 用户，并且经常使用命令行工具 KindleGen 转换电子书格式，可能已经遇到了这个问题：将 macOS 升级到 Catalina 之后，在终端执行 KindleGen 会出现如下所示的错误提示：
```
zsh: bad CPU type in executable: kindlegen
```
问题的原因是 macOS 系统自 Catalina 开始，就停止了对 32 位程序的支持，而KindleGen 官方发布页面却仍未提供 64 位的 KindleGen，这给很多小伙伴带来了不便。那该怎样解决这个问题呢？

虽然 KindleGen 的官方发布页面没有提供 64 位程序，但其实早就存在了。可能是因为亚马逊根据自身业务需求对软件产品的侧重点做了调整，貌似对单独发布 KindleGen 不再感兴趣，转而主推另外一款可视化电子书发布预览工具 [Kindle Previewer](https://www.amazon.com/gp/feature.html?ie=UTF8&docId=1000765261)，用以配合自己的 Kindle Direct Publishing 业务。这款软件有一个将打开的电子书转换为 MOBI 格式的导出功能，这实际上就是利用 KindleGen 来完成的。 

最新版的 Kindle Previewer 3 是 64 位程序，并且能够在 macOS Catalina 中正常使用导出 MOBI 格式的功能，说明集成在里面的 KindleGen 也是 64 位程序。因此，我们的解决方案就出来了——可以直接从 Kindle Previewer 3 的软件包中把这个 64 位的 KindleGen 提取出来使用。下面是具体步骤：

首先，下载亚马逊官方提供的最新的 MAC 版 Kindle Previewer 3 并安装（如果你安装了 macOS 的包管理器 Homebrew，也可通过运行命令 `brew cask install kindle-previewer` 直接安装）。

* Kindle Previewer 3 下载：[官方页面](https://www.amazon.com/gp/feature.html?ie=UTF8&docId=1000765261) ｜ [下载链接](https://s3.amazonaws.com/kindlepreviewer3/KindlePreviewerInstaller.pkg)（约 422MB）

然后，进入“应用程序（Applications）”目录，找到“Kindle Previewer 3.app”这个软件包，在其上点击右键，在弹出菜单中点“显示包内容”，依次进入目录 `Contents/lib/fc/bin` 即可找到 `kindlegen`。
![](/images/kindle-previewer-3-kindlegen-path.png)


为方便起见，你也可以在“终端”上输入以下命令，直接打开 kindlegen 所在的目录：
```
open '/Applications/Kindle Previewer 3.app/Contents/lib/fc/bin/'
```
Kindle Previewer 3 的安装程序约 422MB，安装完成后的软件包更是有 873.3MB 之巨，如果你只想要使用 KindleGen，而不想安装这样一个庞然大物，也可以直接下载书伴为你提取好的 KindleGen 程序。

当然，如果你的电脑已经安装了 Kindle Previewer 3，并且打算长期使用此软件，书伴不建议你将其提取出来，而只需要运行以下这条命令为 KindleGen 创建一个软链接，即可在“终端”上运行它了。
```
ln -s '/Applications/Kindle Previewer 3.app/Contents/lib/fc/bin/kindlegen' /usr/local/bin/kindlegen
```
如此，你就可以在 Catalina 或更新版本的 64 位 macOS 系统中使用 KindleGen了。

> [[教學] macOS 使用者如何取得 64 位元的 KindleGen 程式？](https://www.goston.net/2019/10/22/10927/)