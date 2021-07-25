---
description: 이번주 날씨를 알려주는 api
---

# 이번주 날씨 페이지

## 1\) URL

```text
GET /weather/week
```

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code: `200 OK`

### Description

![](https://user-images.githubusercontent.com/68107000/124441608-ce4ef700-ddb6-11eb-9662-15127c555a16.png)

* resultCode: 응답 코드 \(≠ status code, =서버가 자체적으로 만든 코드, 추후 error code에 정리\)
* errorMessage: 에러 메세지 \(성공 시 SUCCESS 반환\)
* document
  * document.day: 날짜, 1월 1일 \(월\) 과 같은 형식
  * document.amRain: 오전 강수 확률
  * document.amIcon: 오전 날씨 icon URL
  * document.pmRain: 오후 강수 확률
  * document.pmIcon: 오후 날씨 icon URL
  * document.max: 최고 온도
  * document.min: 최저 온도

### Example

```javascript
{
    "resultCode": 200,
    "errorMessage": "SUCCESS",
    "document": [
        {
            "day": "6월 28일 (월)",
            "amRain": 30,
            "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Cloud.png",
            "pmRain": 10,
            "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Cloud.png",
            "max": 29,
            "min": 21
        },
        {
            "day": "6월 29일 (화)",
            "amRain": 30,
            "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Rain-1.png",
            "pmRain": 10,
            "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Rain-1.png",
            "max": 29,
            "min": 21
        },
        {
            "day": "6월 30일 (수)",
            "amRain": 30,
            "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Sun.png",
            "pmRain": 10,
            "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Sun.png",
            "max": 29,
            "min": 21
        },
        {
            "day": "7월 1일 (목)",
            "amRain": 30,
            "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Sun.png",
            "pmRain": 10,
            "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Thunder.png",
            "max": 29,
            "min": 21
        },
        {
            "day": "7월 2일 (금)",
            "amRain": 30,
            "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Cloud.png",
            "pmRain": 10,
            "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Cloud.png",
            "max": 29,
            "min": 21
        },
        {
            "day": "7월 3일 (토)",
            "amRain": 30,
            "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Rain-1.png",
            "pmRain": 10,
            "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Rain-2.png",
            "max": 29,
            "min": 21
        },
        {
            "day": "7월 4일 (일)",
            "amRain": 30,
            "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Rain-2.png",
            "pmRain": 10,
            "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Cloud.png",
            "max": 29,
            "min": 21
        }
    ]
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
|  | JSON\_PARSING\_ERROR | api의 잘못된 응답으로 인한 json 문서 파싱 에러 |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

