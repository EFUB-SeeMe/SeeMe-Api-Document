---
description: 동별 현재 미세먼지 및 초미세먼지 농도를 알려주는 API
---

# 도시별 농도 페이지

## 1\) URL

```text
GET /microdust/city
```

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code : `200 OK`

### Description

| name | type | description |
| :--- | :--- | :--- |
| city | string | 동 이름 |
| dust | int | 동별 미세먼지 농도 |
| microdust | int | 동별 초미세먼지 농도 |

### Example

```java
{
    {
        "city" : 충현동,
        "dust": 23,
        "microdust": 12
    }, 
    {
        "city" : 북아현동,
        "dust": 29,
        "microdust": 22
    }, 
    {
        "city" : 대현동,
        "dust": 19,
        "microdust": 38
    }, 
    {
        "city" : 연희동,
        "dust": 39,
        "microdust": 42
    }
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

