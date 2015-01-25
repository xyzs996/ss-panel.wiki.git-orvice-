### 安装依赖
```
apt-get install python-pip git python-m2crypto 
pip install cymysql 
```

### 安装Shadowsocks
```
git clone -b manyuser https://github.com/mengskysama/shadowsocks.git
cd /shadowsocks/shadowsocks
# 修改数据库信息
vim Config.py
# 跑看看
python server.py  
```

### 使用supervisor进程守护
```
# 安装supervisor
apt-get install python-pip python-m2crypto supervisor
# 编辑文件
vim /etc/supervisor/conf.d/shadowsocks.conf 
```
输入(dir路径记得修改)

```
[program:shadowsocks] 
command=python /dir/server.py -c /dir/config.json
autorestart=true 
user=root 
```

启动

```
service supervisor start 
supervisorctl reload 
```

修改以下文件

```
/etc/profile
/etc/default/supervisor
```
结尾添加3行

```
ulimit -n 51200
ulimit -Sn 4096
ulimit -Hn 8192 
```

debug查看日志

```
supervisorctl tail -f shadowsocks stderr
```


