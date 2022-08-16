## 登陆注册

### 登陆

POST /login/byAccountOrMobile

req
```json
{
    "accountOrMobile": "18026932735",
    "password": "XohImNooBHFR0OVvjcYpJ3NgPQ1qq73WKhHvch0VQtg="
}
```
正常resp
```json
{
    "data": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJuYW1lIjoiYWRtaW4iLCJpZCI6MTU0Nzg5MzYwNTU4OTg0ODA2NSwiZXhwIjoxNjYxMTM4MTM3fQ.2tAyDN1a3jJwl4cEDWF7P4-LOpnTB476hnfsa01F77s",
        "user": {
            "account": "test002",
            "avatar": "xxx.png",
            "certNo": "X001001",
            "cityId": 456,
            "id": 1559175399668744193,
            "mobile": "18012345678",
            "name": "黄小明",
            "provinceId": 123,
            "regionId": 789
        }
    }
}
```
所有需要权限的接口都需要在request header带上key=Auth，value=token的键值对

异常
```json
{
    "data": "",
    "error": "用户不存在或密码错误",
    "status": 400,
    "timestamp": 1660533511147
}
```

### 登出

客户端自行删除token，暂不提供登出接口

### 注册

所有用户均由管理员创建，暂不提供注册接口