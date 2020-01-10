###MySQL启动/停止命令：
```
service mysqld start    启动
service mysqld stop     停止
service mysqld restart  重启
service mysqld reload   重载配置
service mysql status    查看状态
```

###MySQL常用命令
```
mysql -h localhost -u root -p        常用参数：-h 服务器地址，-u 用户名，-p 密码，-P 端口

查看MySQL服务器进程
ps -elf | grep mysqld

服务器进程为mysqld，监听的默认端口为TCP 3306
netstat -anpt | grep mysql

show grants for dba;        查看授权
flush  privileges;          刷新权限
truncate table table_name;  清空表
```

###MySQL备份命令
```
备份命令
mysqldump -hIP地址 -u用户名 -p密码 -d 数据库名 表名 > 绝对路径 + 脚本名;

导出整个数据库结构和数据
mysqldump -hlocalhost -uroot -p123456 database > D:/dump.sql

导出单个数据表结构和数据
mysqldump -hlocalhost -uroot -p123456  database table > D:/dump.sql

导出整个数据库结构（不包含数据）
mysqldump -hlocalhost -uroot -p123456  -d database > D:/dump.sql

导出单个数据表结构（不包含数据）
mysqldump -hlocalhost -uroot -p123456  -d database table > D:/dump.sql

备份所有数据库
mysqldump -hlocalhost -u root -p123456 --all-databases > D:/all_databases.sql

一个命令备份mysql,test多个数据库, 生成的sql文件有创建database mysql和test的语句
mysqldump -hlocalhost -u root -p123456 --database mysql test > D:/more_databases.sql
```
