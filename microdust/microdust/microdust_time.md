---
description: 시간대별 미세먼지 및 초미세먼지 농도를 알려주는 API
---

# 시간대별 추이 페이지

## 1\) URL

```text
GET /microdust/time
```

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code : `200 OK`

### Description

| name | type | description |
| :--- | :--- | :--- |
| time | string | 시간 표시\(24시간제\) |
| dust | int | 시간별 미세먼지 농도 |
| microdust | int | 시간별 초미세먼지 농도 |

### Example

```java
{
    {
        "time" : "현재",
        "dust" : 12,
        "microdust": 10
    },
    {
        "time" : "18시",
        "dust" : 12,
        "microdust": 10
    },
    {
        "time" : "19시",
        "dust" : 10",
        "microdust": 8
    },
    {
        "time" : "20시",
        "dust" :37,
        "microdust": 21
    },
    {
        "time": "21시",
        "dust": 36,
        "microdust": 22
    },
    {
        "time" : "22시",
        "dust": 40,
        "microdust": 22
    }
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

