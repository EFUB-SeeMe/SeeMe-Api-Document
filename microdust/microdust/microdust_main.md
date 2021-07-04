---
description: "미세먼지 페이지 관련 API입니다😊"
---

# 메인 페이지

## 1) URL

```
GET /microdust/main
```



## 2) RESPONSE BODY

### Success http status code

HTTP Status code : `200 OK`



### Description

| name | type | description |
| :---- | :---- | :---- |
| location | string | 위치 |
| icon | string | 아이콘 이미지 URL |
| icon\_code | string | 현재 미세먼지 상태 |
| dust | int | 현재 미세먼지 농도 |
| microdust | int | 현재 초미세먼지 농도 |
| desc | string | 설명 |



### Example

```java
{
	"location": "계양구 병방동",
	"icon": "https://user-images.githubusercontent.com/68107000/124224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png",
	"icon_code": "좋음", 
	"dust": 23,
	"microdust": 15,
	"desc": "야외 활동을 즐겨보세요!",
}
```



## 3) ERROR CODE

| error code | error message         | description    |
| ---------- | --------------------- | -------------- |
| 500        | INTERNAL_SERVER_ERROR | 서버 내부 에러 |

