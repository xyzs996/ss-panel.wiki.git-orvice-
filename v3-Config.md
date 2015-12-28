## 配置

ss-panel v3 配置说明，请根据说明合理选择密码加密方式，认证方式等。

修改站点以及数据库配置
```
vim .env
```

### Auth Driver 认证设置

ss-panel v3支持多种存续用户认证信息的方式，区别如下：

* cookie 同v2的认证方式，不推荐。
* cookie2 强制有效期的cookie认证，有缺陷。
* redis 使用Redis存储，推荐此方式。
* session  php session存储
* db  存储于数据库，安全但是效率不高

推荐使用redis

### 密码加密方式

* md5 不推荐
* sha256+salt 推荐
