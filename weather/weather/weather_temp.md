---
description: 시간대별 기온을 제공하는 api
---

# 시간대별 기온 페이지

## 1) URL

```
GET /weather/temp
```

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code: `200 OK`

### Description

![image](https://user-images.githubusercontent.com/68107000/124440085-31d82500-ddb5-11eb-9a1e-b9cc888a4380.png)

| name | type | description |
| :---: | :---: | :--- |
| time | string | 시간 |
| temperature | int | 온도 |
|    icon     | string | 아이콘 URL  |

### Example

```javascript
{
    [
        {
            "time": "현재",
            "temp": 26,
            "icon": "https://user-images.githubusercontent.com/68107000/124224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png" 
        },
        {
            "time": "18시",
            "temp": 24,
            "icon": "https://user-images.githubusercontent.com/68107000/124224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png"
        },
        {
            "time": "19시",
            "temp": 23,
            "icon": "https://user-images.githubusercontent.com/68107000/124224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png"
        },
        {
            "time": "20시",
            "temp": 22,
            "icon": "https://user-images.githubusercontent.com/68107000/124224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png"
        },
        {
            "time": "21시",
            "temp": 22,
            "icon": "https://user-images.githubusercontent.com/68107000/124224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png"
        },
        {
            "time": "22시",
            "temp": 22,
            "icon": "https://user-images.githubusercontent.com/68107000/174224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png"
        },
        {
            "time": "23시",
            "temp": 21,
            "icon": "https://user-images.githubusercontent.com/68107000/174224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png"
        }
    ]
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

