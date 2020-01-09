###composer命令
```
composer install
composer update
```

###artisan命令
```
php artisan key:generate
php artisan opcache:clear
php artisan schedule:run
php artisan queue:restart

php artisan swoole:action start //开启http服务
php artisan swoole:action stop  //停止
php artisan swoole:action restart  //重新启动
php artisan swoole:action reload  //重新加载，每次改完代码都需运行此命令
php artisan swoole:action infos  //运行信息
```

###清除缓存
```
php artisan route:clear
php artisan config:clear
php artisan cache:clear
```

