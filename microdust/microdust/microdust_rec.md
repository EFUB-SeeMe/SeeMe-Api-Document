---
description: "환기시간을 알려주고 마스크 종류를 추천해주는 API"
---

# 환기시간 및 마스크 추천 페이지

## 1) URL

```
GET /microdust/rec
```



## 2) RESPONSE BODY

### Success http status code

HTTP Status code : `200 OK`



### Description

| name | type | description |
| :---- | :---- | :---- |
| desc | string | 마스크 추천 설명 |
| icon | string | 마스크 아이콘 URL |
| vent\_time | string | 환기 시간\(24시간제\) |
| vent\_bool | boolean | 환기 시간 여부 |



### Example

```java
{
	"desc": "미세먼지 좋아요~ 덴탈마스크 추천!",
	"icon": "https://user-images.githubusercontent.com/68107000/174224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png",
	"vent_time": "12시 30분 ~ 14시 00분",
	"vent_bool": true
}
```



## 3) ERROR CODE

| error code | error message         | description    |
| ---------- | --------------------- | -------------- |
| 500        | INTERNAL_SERVER_ERROR | 서버 내부 에러 |

