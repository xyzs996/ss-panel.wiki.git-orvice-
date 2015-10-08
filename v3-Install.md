### Nginx设置

这里以ss-panel下载至/home/www/ss-panel目录为例进行Nginx配置:

```
    root /home/www/ss-panel/public;

    location / {
        try_files $uri $uri/ /index.php$is_args$args;
    }
```

### 配置

修改站点以及数据库配置
```
config/app.php
config/db.php
```

