
### 调节鼠标移动速度

可以用终端(Spotlight - Terminal)命令来调整：步骤：

 1.打开终端

 2.输入命令查看：
 ```
 defaults read -g com.apple.mouse.scaling
 ```
 , 就可以看到当前的鼠标速度

 3.输入命令修改：
 ```
 defaults write -g com.apple.mouse.scaling 7.5
 ```
  , 就可以修改鼠标速度为 7.5  （数值你可以调 7---9，自己感觉速度，10 以上太快了，不建议）

 4.重启电脑  OK



 **如果是想调节触摸板上光标移动速度:**

 Apple Logo() - 系统偏好设置 - 触摸板 - 跟踪速度(调节即可)