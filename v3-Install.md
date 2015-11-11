### 下载

请在下载页面查看最新版本 https://github.com/orvice/ss-panel/releases

### Nginx设置

这里以ss-panel下载至/home/www/ss-panel目录为例进行Nginx配置:

```
root /home/www/ss-panel/public;

location / {
   try_files $uri $uri/ /index.php$is_args$args;
}    
```

