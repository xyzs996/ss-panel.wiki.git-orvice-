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

#### Auth Driver 认证设置

ss-panel v3支持多种存续用户认证信息的方式，区别如下：

* cookie 同v2的认证方式，不推荐。
* cookie2 强制有效期的cookie认证，有缺陷。
* redis 使用Redis存储，推荐此方式。
* session  php session存储
* db  存储于数据库，安全但是效率不高

推荐使用redis

#### 密码加密方式

* md5 不推荐
* sha256+salt 推荐

