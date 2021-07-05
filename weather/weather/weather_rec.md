---
description: 날씨에 따른 옷을 추천해주는 api, 미완성-고민 중!
---

# OOTD 추천 페이지

## 1\) URL

```text
GET /weather/ootd
```

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code: `200 OK`

### Description

![](https://user-images.githubusercontent.com/68107000/124440901-19b4d580-ddb6-11eb-8c94-67a693c80e91.png)

| name | type | description |
| :---: | :---: | :--- |
| umbrella\_icon | string | 우산 icon URL |
| umbrella\_flag | boolean | 우산 icon을 보여줌/안보여줌 |
| clothes | `cloth pack` list | 나이별 옷차림 |

`cloth pack`

| name | type | description |
| :---: | :---: | :--- |
| age | int | 나이대 |
| top | string | 강수량 |
| bottom | string | 강수 확률 |
| shoes | string | 신발 아이콘 URL |

### Example

```
업데이트 예정
```



## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

