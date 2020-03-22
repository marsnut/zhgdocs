# 签到功能接口文档

### 签到页面数据

```
GET /api/v2/sign/signView
```

响应：

```
Status: 200 Success
```

```json5
{
    "signDay": 1,//当前连续签到天数
    "signList": [
        {
            "day": 1,//第几天
            "get_integral": 1,//获得积分数量
            "is_sign": true,//是否签到
            "today": true //是否今日
        },
        {
            "day": 2,
            "get_integral": 3,
            "is_sign": false,
            "today": false
        },
        {
            "day": 3,
            "get_integral": 5,
            "is_sign": false,
            "today": false
        }
    ]
}
```

### 立即签到

```
POST /api/v2/sign/add
```

响应：

```
Status: 201 Success
```

```json5
{
    "day": 1,//连续签到天数
    "get_integral": 1 //本次获得积分
}
```

### 今日是否签到

```
POST /api/v2/sign/daySign
```

响应：

```
Status: 200 Success
```

```json5
{
    "is_sign": true //是否已签到
}
```

### 我的签到记录

```
POST /api/v2/sign/lists
```
输入：

| 参数 | 类型 | 描述 |
|:----:|----|----|
| `page` | `string` | **可选**，分页，如：1，默认1|
| `page_num` | `string` | **可选**，分页数量，如：15，默认15|


响应：

```
Status: 200 Success
```

```json5
{
    "page": {
        "last_page": 1,
        "current_page": 1,
        "total": 1
    },
    "list": [
        {
            "id": 7,
            "day": 1,
            "get_integral": 1,
            "create_time": "2019-11-04 09:03:39"
        }
    ]
}
```