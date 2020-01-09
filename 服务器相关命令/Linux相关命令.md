###php-fpm服务的方式启动、停止和重启：
```
service php-fpm start
service php-fpm stop
service php-fpm reload
```

###nginx服务的方式启动、停止和重启：
```
service nginx -s reload
service nginx restart
service nginx stop
service nginx start
```

###检查配置文件错误用以下命令
```
php -c /usr/local/php/etc/php.ini
```






