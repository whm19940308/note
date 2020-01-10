###MySQL相关命令：
```
service mysqld start    启动
service mysqld stop     停止
service mysqld restart  重启
service mysqld reload   重载配置
service mysql status    查看状态

查看MySQL服务器进程
ps -elf | grep mysqld

服务器进程为mysqld，监听的默认端口为TCP 3306
netstat -anpt | grep mysql


```
