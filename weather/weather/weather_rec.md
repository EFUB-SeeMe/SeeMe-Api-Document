---
description: 날씨에 따른 옷을 추천해주는 api
---

# OOTD 추천 페이지

## 1\) URL

```text
GET /weather/ootd
```

## 2\) RESPONSE BODY

| name | type | description |
| :---: | :---: | :--- |
| umbrella\_icon | string | 우산 icon URL |
| umbrella\_flag | boolean | 우산 icon을 보여줌/안보여줌 |
| clothes | `cloth pack` list | 나이별 옷차림 |

`cloth pack`

| name | type | description |
| :---: | :---: | :--- |
| age | int | 시간 |
| top | string | 강수량 |
| bottom | string | 강수 확률 |
| shoes | string | 신발 아이콘 URL |

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

