###nginx服务的方式启动、停止和重启：
```
service nginx -s reload 加载配置重启
service nginx restart 重启
service nginx stop  立即停止
nginx -s quit  优雅停止,建议使用
service nginx start 开启
```

###nginx服务的方式启动、停止和重启：
```
查询nginx主进程号
ps -ef | grep nginx 

重新打开日志文件命令
nginx -s reopen
```


