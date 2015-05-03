# ss-panel 中文安装教程

 

### 从 0.X 升级
如果你原来版本是0.X 请查阅 
[Read this](https://github.com/orvice/ss-panel/blob/master/upgrade_to_v2.md)

### 系统要求
* PHP >= 5.4
* PDO Extension

### 安装
* 导入sql目录下的所有sql文件到数据库
* 将 lib/config-sample.php 重命名为 config.php，并编辑数据库信息.
* 上传整个目录

### Admin
* The user who uid is 1 is Admin by default.
* You can Add User ID into table 'ss_user_admin'

### Send mail using mail-gun
Run:

```
$ curl -sS https://getcomposer.org/installer | php
$ php composer.phar  install
```

 
