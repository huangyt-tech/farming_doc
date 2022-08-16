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