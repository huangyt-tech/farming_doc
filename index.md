### 通用规则
1. 如无特殊说明，所有接口请求和返回均为json
2. 除服务器遇到无法处理异常，所有请求返回Http Response Code均为200
3. 返回结构体为
```json
{
    "data": {
    },
    "error": "",
    "status": 0,
    "timestamp": 1660533337954
}
```
其中：
* status表示接口调用结果，status=0为正常，403为未登录，401为未授权。其他值由接口约定。
* data为返回业务数据。
* error为错误信息，status=0时为空字符串，否则返回错误信息。
* timestamp为返回时服务器时间戳。

## 登陆状态

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

目前后端不提供登出接口，由客户端自行删除token

## 基础数据

### 省市区

GET /base/area

req
```json

```

### 监管类型

GET /base/supervise/types

resp
```json
{
    "data": [
        {
            "icon": "png",
            "id": 1559097812837842946,
            "name": "农产品监管"
        }
    ]
}
```

### 擅长业务

GET /base/supervise/subjects

resp
```json
{
    "data": [
        {
            "id": 1559097812837842946,
            "subject": "农产品"
        }
    ]
}
```

### 检查事项

### 检查子业务

### 检查内容项

## 用户管理

### 创建用户

POST /user/create

req
```json
{
    "account": "test001",
    "name": "黄小明",
    "certNo": "X001001",
    "mobile": "18012345678",
    "avatar": "xxx.png",
    "provinceId": 123,
    "cityId": 456,
    "regionId": 789,
    "union": "一队",
    "subjectIds": [1559097812837842946, 1559097812837842947]
}
```

resp
```json
{
    "data": {
        "account": "test001",
        "avatar": "xxx.png",
        "certNo": "X001001",
        "cityId": 456,
        "id": 1559169312840253442,
        "mobile": "18012345678",
        "name": "黄小明",
        "provinceId": 123,
        "regionId": 789,
        "subjects": [
            {
                "id": 1559169313108688898,
                "subject": "农产品"
            },
            {
                "id": 1559169313108688899,
                "subject": "农资"
            }
        ]
    }
}
```
异常1，账号已存在
```json
{
    "data": "",
    "error": "账号已存在",
    "status": 400001,
    "timestamp": 1660570234069
}
```
异常2，账号已存在
```json
{
    "data": "",
    "error": "手机号码已存在",
    "status": 400002,
    "timestamp": 1660570344864
}
```

### 用户信息
GET /user/getById?id=

resp
```json
{
    "data": {
        "account": "test001",
        "avatar": "xxx.png",
        "certNo": "X001001",
        "cityId": 456,
        "id": 1559169312840253442,
        "mobile": "18012345678",
        "name": "黄小明",
        "provinceId": 123,
        "regionId": 789,
        "subjects": [
            {
                "id": 1559169313108688898,
                "subject": "农产品"
            }
        ]
    }
}
```

### 用户列表

### 修改用户资料

## 监管对象