###php-fpm服务的方式启动、停止和重启：
```
service php-fpm start
service php-fpm stop
service php-fpm reload
```

###检查配置文件错误用以下命令
```
php -c /usr/local/php/etc/php.ini
```

###系统
```
uname -a
查看内核/操作系统/CPU信息
 
head -n 1 /etc/issue
查看操作系统版本
 
cat /proc/cpuinfo
查看CPU信息
 
hostname
查看计算机名

lsmod
列出加载的内核模块
 
env
查看环境变量
```

###资源
```
free -m
查看内存使用量和交换区使用量

df -h
查看各分区使用情况
 
du -sh 
查看指定目录的大小
 
grep MemTotal /proc/meminfo
查看内存总量
 
grep MemFree /proc/meminfo
查看空闲内存量
 
uptime
查看系统运行时间、用户数、负载
 
cat /proc/loadavg
查看系统负载
```

###磁盘和分区
```
mount | column -t 
查看挂接的分区状态 
 
fdisk -l 
查看所有分区
 
swapon -s 
查看所有交换分区
```

###网络
```
ifconfig
查看所有网络接口的属性
 
iptables -L
查看防火墙设置route -n
 
查看路由表
netstat -lntp
 
查看所有监听端口
netstat -antp
 
查看所有已经建立的连接
 
netstat -s
查看网络统计信息5. 进程ps -ef
查看所有进程
 
top
实时显示进程状态
 
ps -ef | grep 进程名/进程id
查看指定进程
```

###用户
```
w
查看活动用户
 
id 
查看指定用户信息
 
last
查看用户登录日志
 
cut -d: -f1 /etc/passwd
查看系统所有用户
 
cut -d: -f1 /etc/group
查看系统所有组
```

###服务
```
chkconfig --list
列出所有系统服务
 
chkconfig --list | grep on
列出所有启动的系统服务
 
chmod +x FileName
给某个文件授予执行权限
 
tail -100f log.log
实时输出最新100行日志
```

###查找文件
```
find / -name FielName
在根目录下查找名为FileName的文件
```



