## 农业项目接口文档

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

### [注册登陆](login.html)

### [基础数据](base.html)

### [用户管理](user.html)
