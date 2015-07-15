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

### 后台
* 默认情况下，user表中uid为1的用户为管理员
* 添加管理员可以在 'ss_user_admin' 表中添加用户UID
* 默认管理帐号: first@blood.com 密码 1993

### 安装各种依赖
ssh到vps下，cd到网站目录，执行如下命令:

```
$ curl -sS https://getcomposer.org/installer | php
$ php composer.phar  install
```

 
