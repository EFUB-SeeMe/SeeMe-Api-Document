---
description: 시간대별 강수량을 알려주는 api
---

# 시간대별 강수량 페이지

## 1\) URL

```text
GET /weather/rain
```

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code: `200 OK`

### Description

![](https://user-images.githubusercontent.com/68107000/124441433-a19adf80-ddb6-11eb-9d14-9d8736b524ba.png)

| name | type | description |
| :---: | :---: | :--- |
| time | string | 시간 |
| rainfall | int | 강수량 |
| percent | int | 강수 확률 |
| icon | string | 아이콘 URL |

### Example

```javascript
{
    [
        {
            "time": "현재",
            "rain": 30,
            "percent": 60,
            "icon": "https://user-images.githubus{ercontent.com/68107000/174224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png"
        },
        {
            "time": "18시",
            "rain": 30,
            "percent": 60,
            "icon": "https://user-images.githubusercontent.com/68107000/174224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png"
        },
        {
            "time": "19시",
            "rain": 30,
            "percent": 60,
            "icon": "https://user-images.githubusercontent.com/68107000/174224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png"
        },
        {
            "time": "20시",
            "rain": 30,
            "percent": 60,
            "icon": "https://user-images.githubusercontent.com/68107000/174224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png"
        },
        {
            "time": "21시",
            "rain": 30,
            "percent": 60,
            "icon": "https://user-images.githubusercontent.com/68107000/174224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png"
        }
    ]
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

