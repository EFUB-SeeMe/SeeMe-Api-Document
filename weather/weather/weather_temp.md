---
description: 시간대별 기온을 제공하는 API
---

# 시간대별 기온 페이지

## 1\) URL

```text
GET /weather/temp
```

## 2\) RESPONSE BODY

### Success http status code

`200 OK`

### Description

![](https://user-images.githubusercontent.com/68107000/124440085-31d82500-ddb5-11eb-9a1e-b9cc888a4380.png)

| name | type | description |
| :---: | :---: | :--- |
| time | string | 시간 |
| temperature | string | 온도 |
| icon | string | 아이콘 URL |

### Example

```javascript
[
  {
    "time": "현재",
    "temperature": "25°",
    "icon": "https://seeme.png"
  },
  {
    "time": "10시",
    "temperature": "26°",
    "icon": "https://seeme.png"
  },
  {
    "time": "11시",
    "temperature": "27°",
    "icon": "https://seeme.png"
  },
  {
    "time": "12시",
    "temperature": "28°",
    "icon": "https://seeme.png"
  },
  {
    "time": "13시",
    "temperature": "29°",
    "icon": "https://seeme.png"
  },
  {
    "time": "14시",
    "temperature": "29°",
    "icon": "https://seeme.png"
  },
  {
    "time": "15시",
    "temperature": "29°",
    "icon": "https://seeme.png"
  },
  {
    "time": "18시",
    "temperature": "28°",
    "icon": "https://seeme.png"
  },
  {
    "time": "21시",
    "temperature": "28°",
    "icon": "https://seeme.png"
  },
  {
    "time": "0시",
    "temperature": "27°",
    "icon": "https://seeme.png"
  }
]
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

