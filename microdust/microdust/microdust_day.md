---
description: '요일별 오전, 오후 미세먼지 및 초미세먼지 농도를 알려주는 API'
---

# 요일별 추이 페이지

## 1\) URL

```text
GET /microdust/day
```

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code : `200 OK`

### Description

![image](https://user-images.githubusercontent.com/68282057/124726655-e787ad00-df48-11eb-99f2-95855c82d781.png)

| name | type | description |
| :--- | :--- | :--- |
| dust\_am | int | 오전 평균 미세먼지 농도 |
| microdust\_am | int | 오전 평균 초미세먼지 농도 |
| dust\_pm | int | 오후 평균 미세먼지 농도 |
| microdust\_pm | int | 오후 평균 초미세먼지 농도 |
| date | string | 날짜 |

### Example

```java
{
    {
        "dust_am": 32,
        "microdust_am": 35,
        "dust_pm": 18,
        "microdust_pm": 30,
        "date": "06.27" 
    }
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

