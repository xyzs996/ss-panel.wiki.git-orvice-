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

pytheon大概是这样写：
```
conn = http.client.HTTPConnection("loli.xxx")

headers = {
    'Token': "MY_TOKEN" 
    }

conn.request("GET", "/mu/v2/", headers=headers)

res = conn.getresponse()
data = res.read()
```

