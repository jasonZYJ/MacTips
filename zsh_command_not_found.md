#### 解决 zsh: command not found: node
* 解决方法一

  打开`~.zshrc`
  `vim .zshrc`
  添加一行脚本
  `source ~.bash_profile`
* 解决方法二
  由于笔者没有.bash_profile这一文件，但是网上搜索到的诸多教程都是解决方法一。看过几篇文章后突然想到我将nvm、node等环境配置全部写在了bashrc里边，然后就试着运行了一下‘source .bashrc’,结果报了一大堆错误。突然想到，我用的是zsh，bash当然会报错（卒）。
  所以，解决方法二，就是将.bashrc中关于node的配置copy到.zshrc里边。然后再
  `source ~.zshrc`
  问题就解决了。
  就以node举栗(笔者使用nvm管理的node)：
  将`.bashrc`中的
  ```
  export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```
copy到`~.zshrc`下就可以啦。


附:
#### Mac zsh: command not found zsh 所有命令在终端失效
* 方法一：
```
PATH=/bin:/usr/bin:/usr/local/bin:${PATH}
export PATH
```
* 方法二：
```
exec /bin/zsh
```
* 方法三：
```
exec /usr/bin/zsh
```
