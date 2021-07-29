---
description: '요일별 오전, 오후 미세먼지 및 초미세먼지 농도를 알려주는 api'
---

# 요일별 추이 페이지

## 1\) URL

### Request URL

```text
GET /microdust/day
```

\* 요청 파라미터가 없을 때, _서울특별시 서대문구 대현동_의 값을 보여줍니다.

### Request Parameter1

| parameter | requirement | description |
| :---: | :---: | :--- |
| lat | N | 위도 |
| lon | N | 경도 |

```text
GET /microdust/day/lat=37.5145963013281&lon=126.9754626313914
```

### Request Parameter 2

| parameter | requirement | description |
| :---: | :---: | :--- |
| code | N | 행정동코드 |

```text
GET /microdust/day?code=2824510700
```

\* 검색 시 해당 파라미터를 이용하여 호출할 수 있습니다.

## 2\) RESPONSE BODY

![day](../../.gitbook/assets/.png%20%283%29.png)

### Success http status code

HTTP Status code : `200 OK`

### Description

| name | type | description |
| :---: | :---: | :---: |
| dust | int | 평균 미세먼지 농도 |
| microdust | int | 평균 초미세먼지 농도 |
| date | string | 날짜 |

### Example

```java
[
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
]
```

## 3\) ERROR CODE

| error code | error message | description |
| :---: | :---: | :---: |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

