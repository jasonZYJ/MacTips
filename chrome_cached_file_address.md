#### Chrome浏览器的缓存文件位置在哪

打开 Chrome 浏览器然后在地址栏输入 `chrome://version`
按下回车键，chrome浏览器中会显示个人资料路径，复制该路径
可以删除此路径里面的 cache文件夹

![](/images/chrome_cached_file_address.jpg)

其中的**个人资料路径**里面有`History`文件,其是 SQLite文件,可以用 **DB Browser for SQLite**打开,显示浏览历史记录
