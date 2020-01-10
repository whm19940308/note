###crontab定时执行任务命令：
```
当安装完成操作系统之后，默认便会启动此任务调度命令。
crond 命令每分锺会定期检查是否有要执行的工作，如果有要执行的工作便会自动执行该工作。
而 linux 任务调度的工作主要分为以下两类：

1、系统执行的工作：系统周期性所要执行的工作，如备份系统数据、清理缓存
2、个人执行的工作：某个用户定期要做的工作，例如每隔10分钟检查邮件服务器是否有新信，这些工作可由每个用户自行设置
语法
crontab [ -u user ] file
或
crontab [ -u user ] { -l | -r | -e }

说明：
crontab 是用来让使用者在固定时间或固定间隔执行程序之用，换句话说，也就是类似使用者的时程表。
-u user 是指设定指定 user 的时程表，这个前提是你必须要有其权限(比如说是 root)才能够指定他人的时程表。如果不使用 -u user 的话，就是表示设定自己的时程表

service crond start    启动服务
service crond stop     关闭服务
service crond restart  重启服务
service crond reload   重新载入配置
service crond status   查看服务状态

crontab -l   查看crontab
crontab -e   编辑crontab
crontab -r   删除crontab

minute   hour   day   month   week  year  [user]  [command]
crontab表达式说明：
*    *    *    *    *    *     [user]   [command]
-    -    -    -    -    -
|    |    |    |    |    |
|    |    |    |    |    + 年 [可选]
|    |    |    |    +----- 星期 (0 - 7) (Sunday=0 or 7)
|    |    |    +---------- 月 (1 - 12)
|    |    +--------------- 日 (1 - 31)
|    +-------------------- 时 (0 - 23)
+------------------------- 分 (0 - 59)

时间格式如下：

f1 f2 f3 f4 f5 program
1. 其中 f1 是表示分钟，f2 表示小时，f3 表示一个月份中的第几日，f4 表示月份，f5 表示一个星期中的第几天。program 表示要执行的程序
2. 当 f1 为 * 时表示每分钟都要执行 program，f2 为 * 时表示每小时都要执行程序，其馀类推
3. 当 f1 为 a-b 时表示从第 a 分钟到第 b 分钟这段时间内要执行，f2 为 a-b 时表示从第 a 到第 b 小时都要执行，其馀类推
4. 当 f1 为 */n 时表示每 n 分钟个时间间隔执行一次，f2 为 */n 表示每 n 小时个时间间隔执行一次，其馀类推
5. 当 f1 为 a, b, c,... 时表示第 a, b, c,... 分钟要执行，f2 为 a, b, c,... 时表示第 a, b, c...个小时要执行，其馀类推

crontab命令实例
0 0 L * *        每月的最后1天执行
* * * * *        每1分钟执行一次
*/10 * * * *     每隔10分钟执行一次
0 */1 * * *      每隔1小时执行一次
30 21 * * *      每晚的21:30执行
3,15 * * * *     每小时的第3和第15分钟执行
3,15 8-11 * * *  在上午8点到11点的第3和第15分钟执行

crontab命令示例
0 * * * * /bin/ls                                           每月每天每小时的第 0 分钟执行一次 /bin/ls
* * * * * curl https://www.baidu.com &>/dev/null            每分钟访问一次baidu
0 */2 * * * /sbin/service httpd restart                     每两个小时重启一次apache 
50 7 * * * /sbin/service sshd start                         每天7：50开启ssh服务 
50 22 * * * /sbin/service sshd stop                         每天22：50关闭ssh服务 
0 0 1,15 * * fsck /home                                     每月1号和15号检查/home 磁盘 
1 * * * * /home/bruce/backup                                每小时的第一分执行 /home/bruce/backup这个文件 
00 03 * * 1-5 find /home "*.xxx" -mtime +4 -exec rm {} \;   每周一至周五3点钟，在目录/home中，查找文件名为*.xxx的文件，并删除4天前的文件
30 6 */10 * * ls                                            每月的1、11、21、31日是的6：30执行一次ls命令
0 6-12/3 * 12 * /usr/bin/backup                             在 12 月内, 每天的早上 6 点到 12 点，每隔 3 个小时 0 分钟执行一次 /usr/bin/backup
0 17 * * 1-5 mail -s "hi" alex@domain.name < /tmp/maildata  周一到周五每天下午 5:00 寄一封信给 alex@domain.name                             
20 0-23/2 * * * echo "haha"                                 每月每天的午夜0点20分,2点20分, 4点20分....执行 echo "haha"
```
