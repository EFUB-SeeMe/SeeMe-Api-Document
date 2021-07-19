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
| dust | int | 평균 미세먼지 농도 |
| microdust | int | 평균 초미세먼지 농도 |
| date | string | 날짜 |

### Example

```java
{
  {
    "dust": 19,
    "microdust": 19,
    "date": "07.18"
  },
  {
    "dust": 21,
    "microdust": 20,
    "date": "07.19"
  },
  {
    "dust": 28,
    "microdust": 26,
    "date": "07.20"
  },
  {
    "dust": 22,
    "microdust": 21,
    "date": "07.21"
  },
  {
    "dust": 21,
    "microdust": 20,
    "date": "07.22"
  }
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

