---
description: "날씨 페이지 관련 API 입니다\U0001F60E"
---

# 메인 페이지

## 1\) URL

```text
GET /weather/main
```

## 2\) RESPONSE BODY

### Success http status code

`200 OK`

### Description

![image](https://user-images.githubusercontent.com/68107000/124440780-f427cc00-ddb5-11eb-859f-a3d9d53492eb.png)

| name | type | description |
| :---: | :---: | :--- |
| location | string | 위치 |
| icon | string | 아이콘 URL |
| icon\_code | string | 아이콘 설명 |
| curr\_temp | int | 현재 온도 |
| sens\_temp | int | 체감 온도 |
| max | int | 최고 온도 |
| min | int | 최저 온도 |
| desc | string | 오늘 날씨에 대한 설명 |
| comp | string | 전날과의 비교 설명 |

### Example

```javascript
{
    "location": "계양구 병방동",
    "icon": "https://user-images.githubusercontent.com/68107000/124224687-19f86b00-db41-11eb-9090-d2b32f38fa67.png",
    "icon_code": "흐림",
    "curr_temp": 26,
    "sens_temp": 28,
    "max": 29,
    "min": 20,
    "desc": "오늘은 오후 6시에 소나기가 내려요\n우르르 쾅 !",
    "comp": "어제보다 2℃ 낮아요"
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

