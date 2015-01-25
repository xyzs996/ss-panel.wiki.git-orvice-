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
