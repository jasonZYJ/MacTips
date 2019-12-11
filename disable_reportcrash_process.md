### Mac 系统禁用 ReportCrash 进程


晚上在 terminal 里敲代码，发现系统异常的卡顿。在 Activity Monitor 里发现 ReportCrash 进程占用了大量的 CPU

不断发送崩溃报告说明不断有进程在崩溃，先看一下系统日志

要怎么定位是哪个进程crash了呢？

办法是查看system.log，它的位置：`/var/log/system.log`，我看了一下我的（可以用`console(控制台)`这个应用打开）：

```
$ tail -F /var/log/system.log

Feb  5 21:09:01 Sun-Zhongweis-MacBook-Pro com.apple.xpc.launchd[1] (com.alipay.DispatcherService[11484]): Service exited due to signal: Trace/BPT trap: 5 sent by exc handler[0]
Feb  5 21:09:01 Sun-Zhongweis-MacBook-Pro com.apple.xpc.launchd[1] (com.alipay.DispatcherService): Service only ran for 2 seconds. Pushing respawn out by 8 seconds.
Feb  5 21:09:09 Sun-Zhongweis-MacBook-Pro com.apple.xpc.launchd[1] (com.apple.nowplayingtouchui): Service only ran for 0 seconds. Pushing respawn out by 10 seconds.
Feb  5 21:09:11 Sun-Zhongweis-MacBook-Pro com.apple.xpc.launchd[1] (com.alipay.DispatcherService[11486]): Service exited due to signal: Trace/BPT trap: 5 sent by exc handler[0]
Feb  5 21:09:11 Sun-Zhongweis-MacBook-Pro com.apple.xpc.launchd[1] (com.alipay.DispatcherService): Service only ran for 2 seconds. Pushing respawn out by 8 seconds.
Feb  5 21:09:11 Sun-Zhongweis-MacBook-Pro com.apple.xpc.launchd[1] (com.apple.ReportCrash.Root[11487]): Endpoint has been activated through legacy launch(3) APIs. Please switch to XPC or bootstrap_check_in(): com.apple.ReportCrash.DirectoryService
Feb  5 21:09:11 Sun-Zhongweis-MacBook-Pro ReportCrash[11487]: assertion failed: 16D32: libsystem_trace.dylib + 76912 [6D34D1EA-2A3C-3D2D-803E-A666E6AEEE52]: 0x0
Feb  5 21:09:19 --- last message repeated 6 times ---
Feb  5 21:09:19 Sun-Zhongweis-MacBook-Pro com.apple.xpc.launchd[1] (com.apple.nowplayingtouchui): Service only ran for 0 seconds. Pushing respawn out by 10 seconds.
Feb  5 21:09:21 Sun-Zhongweis-MacBook-Pro com.apple.xpc.launchd[1] (com.alipay.DispatcherService[11489]): Service exited due to signal: Trace/BPT trap: 5 sent by exc handler[0]
Feb  5 21:09:21 Sun-Zhongweis-MacBook-Pro com.apple.xpc.launchd[1] (com.alipay.DispatcherService): Service only ran for 2 seconds. Pushing respawn out by 8 seconds.
```

我的天，每隔几秒 com.alipay.DispatcherService, com.apple.nowplayingtouchui 这两个妖孽就作怪一次。实在是太卡了，先不调查这两个可疑进程了，先把 ReportCrash 解决掉。

####禁用 ReportCrash

直接干掉进程肯定不管用，从名字就知道这个进程会自动被触发，除非修改系统配置。

Google 了一下，发现很简单，在 terminal 里执行
```
launchctl unload -w /System/Library/LaunchAgents/com.apple.ReportCrash.plist
sudo launchctl unload -w /System/Library/LaunchDaemons/com.apple.ReportCrash.Root.plist
```
再观察 Activity Monitor，会发现 ReportCrash 进程不再出现了。系统又恢复了如丝般顺滑的状态。

重新启用的方法（估计我这辈子都不会启动这货）
```
launchctl load -w /System/Library/LaunchAgents/com.apple.ReportCrash.plist
sudo launchctl load -w /System/Library/LaunchDaemons/com.apple.ReportCrash.Root.plist
```