## Mu API V2


 
### 基本说明

需要在ss程序保存3个信息：

* url api访问的主要url，例如 loli.xxx/mu/v2/
* token 每次访问需要携带的token
* node_id 节点id


api根据http code来判断返回情况。

* 200 即请求成功，可以继续解析json数据。
* 401 授权无效，token被服务器拒绝。
* 400 请求无效，若更新流量返回400即流量更新失败。

### 授权

在请求的Header携带Token

curl表示为:

```
curl -X GET -H "Token: MY_TOKEN"  "http://loli.xxx/mu/v2/"
```

python大概是这样写：
```
conn = http.client.HTTPConnection("loli.xxx")

headers = {
    'Token': "MY_TOKEN" 
    }

conn.request("GET", "/mu/v2/", headers=headers)

res = conn.getresponse()
data = res.read()
```


### 接口

#### GET /users

返回值大概是这样
```
{
    "msg": "ok",
    "data": [
        {
            "id": 1,
            "passwd": "123gxopp",
            "t": 1463581379,
            "u": 2048,
            "d": 2048,
            "transfer_enable": 23166189568,
            "port": 21567,
            "switch": 1,
            "enable": 1,
            "method": "rc4-md5"
        },
        {
            "id": 1,
            "passwd": "123gxopp",
            "t": 1463581379,
            "u": 2048,
            "d": 2048,
            "transfer_enable": 23166189568,
            "port": 21567,
            "switch": 1,
            "enable": 1,
            "method": "rc4-md5"
        }
    ]
}
```

#### POST /users/{id}/traffic

{id} 为 /users 接口中返回的id

更新流量post以下数据:

* u  上传流量
* d  下载流量
* node_id 节点id

curl example:
```
curl -X POST -H "Token: MY_TOKEN" -H "Cache-Control: no-cache"  -H "Content-Type: application/x-www-form-urlencoded" -d 'u=1024&d=1024&node_id=1' "http://loli.xxx/mu/v2/users/1/traffic"
```

python3 example:

```
import http.client

conn = http.client.HTTPConnection("loli.xxx")

payload = "u=1024&d=1024&node_id=1"

headers = {
    'Token': "MY_TOKEN",
    'cache-control': "no-cache", 
    'content-type': "application/x-www-form-urlencoded"
    }

conn.request("POST", "/mu/v2/users/1/traffic", payload, headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```

