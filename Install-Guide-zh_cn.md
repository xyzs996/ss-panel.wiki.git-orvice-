# ss-panel v2 中文安装教程

注意： 这是v2版本安装教程，v2目前不在继续更新，仅做bug修复。

### 从 0.X 升级
如果你原来版本是0.X 请查阅 
[Read this](https://github.com/orvice/ss-panel/blob/master/upgrade_to_v2.md)

### 系统要求
* PHP >= 5.4
* PDO Extension

### 下载

请从发布页面下载  https://github.com/orvice/ss-panel/releases

### 安装
* 导入sql目录下的所有sql文件到数据库
* 将 lib/config-sample.php 重命名为 config.php，并编辑数据库信息.
* 上传整个目录

### 后台
* 默认情况下，user表中uid为1的用户为管理员
* 添加管理员可以在 'ss_user_admin' 表中添加用户UID
* 默认管理帐号: first@blood.com 密码 1993

### 新版密码加密方式说明
当使用新的加密方式「带salt的sha256」加密，由于每个站点的$salt值都不同，所以初始密码「1993」是没有用的，安装完成后，访问
```
/pwd.php?pwd=1993
```
将获得的字符串更新到数据库user表的pass字段。

注意：
* $salt 不可随意修改！
* 如果原来为2.4之前的版本，需要将pass字段的长度修改为64

### 安装各种依赖
ssh到vps下，cd到网站目录，执行如下命令:

```
$ curl -sS https://getcomposer.org/installer | php
$ php composer.phar  install
```

 
