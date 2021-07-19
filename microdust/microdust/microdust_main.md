---
description: "미세먼지 페이지 관련 API입니다\U0001F60A"
---

# 메인 페이지

## 1\) URL

### Request URL

```text
GET /microdust/main
```

### Request Parameter

| parameter | requirement | description |
| :---: | :---: | :--- |
| lat | N | 위도 |
| lon | N | 경도 |

```text
GET /microdust/main?lat=37.5145963013281&lon=126.9754626313914
```

\* lat 또는 lon 둘 중 하나라도 값이 없는 경우에는, _서울특별시 용산구 이촌동_의 값을 보여줍니다.

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code: `200 OK`

### Description

![image](https://user-images.githubusercontent.com/68282057/124726729-fa01e680-df48-11eb-86e2-258ff2d4633b.png)

| name | type | description |
| :--- | :--- | :--- |
| address | string | 위치 |
| grade | int | 현재 미세먼지 등급 좋음, 보통, 나쁨, 매우나쁨 의 값을 나타냄 |
| gradeIcon | string | 아이콘 이미지 URL |
| pm10 | int | 현재 미세먼지 농도 |
| pm25 | int | 현재 초미세먼지 농도 |
| desc | string | 설명 |

### Example

```java
{
  "address": "서울특별시 용산구 이촌동",
  "grade": "좋음",
  "gradeIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/microdust/microdust.png",
  "pm10": 15,
  "pm25": 6,
  "desc": "야외 활동을 즐겨보세요 !"
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

