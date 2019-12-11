###Mac 上 brew 安装Tomcat

首先保证brew命令能够正常使用；

1.搜索tomcat是否存在：
`brew search tomcat`

2.安装tomcat：
`brew install tomcat`

3.检查是否安装成功：
`catalina -h`

4.运行tomcat：
`catalina run`

Tomcat的默认端口是`8080`，如果运行成功可通过`http://localhost:8080`访问

`webapp`的根目录`CATALINA_HOME`为:`/usr/local/Cellar/tomcat/7.0.33/libexec/webapps/ROOT/`

