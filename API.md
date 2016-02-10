## ss-panel v3 api

ss-panel 提供一套简单api，用户获取用户信息。

### 授权

获取token后，请求是url带上 ?access_token=TOKEN

### POST /api/token

获取token接口，参数:
* email
* passwd

### GET /api/token/{token}

获取token信息

### GET /api/node

获取node信息。

### GET /api/user/{userid}

获取用户的信息