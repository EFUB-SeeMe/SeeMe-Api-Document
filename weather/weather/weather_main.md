---
description: "현재 날씨, 이번주 날씨 정보를 반환하는 api\U0001F60E"
---

# 메인 페이지

## 1\) URL

```text
GET /weather/main
```

### Request Parameter1

| parameter | requirement | description |
| :---: | :---: | :--- |
| lat | N | 위도 |
| lon | N | 경도 |

```text
GET /weather/main?lat=37.5145963013281&lon=126.9754626313914
```

### Request Parameter 2

| parameter | requirement | description |
| :---: | :---: | :--- |
| code | N | 행정 구역 코드 |

```text
GET /weather/main?code=2824510700
```

\* 검색 시 해당 파라미터를 이용하여 호출할 수 있습니다.

## 2\) RESPONSE BODY

### Success http status code

`200 OK`

### Description

![](https://user-images.githubusercontent.com/68107000/124440780-f427cc00-ddb5-11eb-859f-a3d9d53492eb.png)

* currentInfo
  * currentInfo.resultCode: 응답 코드 \(200 = SUCCESS, 500 = ERROR\)
  * currentInfo.errorMessage: 에러 메세지 \(성공 시 SUCCESS 반환\)
  * currentInfo.document
    * currentInfo.document.currTemp: 현재 온도
    * currentInfo.document.feelTemp: 체감 온도
    * currentInfo.document.iconDesc: 아이콘 설명
    * currentInfo.document.icon:  아이콘 URL
    * currentInfo.document.comp: 전날과의 비교설명
* minmaxInfo
  * minmaxInfo.resultCode: 응답 코드 \(200 = SUCCESS, 500 = ERROR\)
  * minmaxInfo.errorMessage: 에러 메세지 \(성공 시 SUCCESS 반환\)
  * minmaxInfo.document
    * minmaxInfo.document.max: 최고 온도
    * minmaxInfo.document.min: 최저 온도
    * minmaxInfo.document.desc: 오늘 날씨 설명

![](https://user-images.githubusercontent.com/68107000/124441608-ce4ef700-ddb6-11eb-9662-15127c555a16.png)

* weekInfo
  * weekInfo.resultCode: 응답 코드 \(200 = SUCCESS, 500 = ERROR\)
  * weekInfo.errorMessage: 에러 메세지 \(성공 시 SUCCESS 반환\)
  * weekInfo.document
    * weekInfo.document.day: 날짜, 1월 1일 \(월\) 과 같은 형식
    * weekInfo.document.amRain: 오전 강수량
    * weekInfo.document.amPercent: 오전 강수 확률
    * weekInfo.document.amIcon: 오전 날씨 icon URL
    * weekInfo.document.pmRain: 오후 강수량
    * weekInfo.document.pmPercent: 오후 강수 확률
    * weekInfo.document.pmIcon: 오후 날씨 icon URL
    * weekInfo.document.max: 최고 온도
    * weekInfo.document.min: 최저 온도

### Example

```javascript
{
    "currentInfo": {
        "resultCode": 200,
        "errorMessage": "SUCCESS",
        "document": {
            "currTemp": 29,
            "feelTemp": 31,
            "iconDesc": "흐림",
            "icon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Cloud.png",
            "comp": "오늘은 어제와 비슷한 날씨가 예상됩니다."
        }
    },
    "minmaxInfo": {
        "resultCode": 200,
        "errorMessage": "SUCCESS",
        "document": {
            "min": 24,
            "max": 33,
            "desc": "약간 흐리고 따뜻함"
        }
    },
    "weekInfo": {
        "resultCode": 200,
        "errorMessage": "SUCCESS",
        "document": [
            {
                "day": "07월29일 (금)",
                "amRain": 0,
                "amRainPercent": 50,
                "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Sun-Rain-2.png",
                "pmRain": 0,
                "pmRainPercent": 50,
                "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Sun-Rain-2.png",
                "max": 33,
                "min": 24
            },
            {
                "day": "07월30일 (토)",
                "amRain": 0,
                "amRainPercent": 11,
                "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Hot.png",
                "pmRain": 0,
                "pmRainPercent": 11,
                "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Hot.png",
                "max": 36,
                "min": 25
            },
            {
                "day": "07월31일 (일)",
                "amRain": 0,
                "amRainPercent": 25,
                "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Sun.png",
                "pmRain": 0,
                "pmRainPercent": 25,
                "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Sun.png",
                "max": 33,
                "min": 25
            },
            {
                "day": "08월01일 (금)",
                "amRain": 0,
                "amRainPercent": 19,
                "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Cloudy-Sun.png",
                "pmRain": 0,
                "pmRainPercent": 19,
                "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Cloudy-Sun.png",
                "max": 32,
                "min": 24
            },
            {
                "day": "08월02일 (토)",
                "amRain": 8,
                "amRainPercent": 65,
                "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Rain-1.png",
                "pmRain": 8,
                "pmRainPercent": 65,
                "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Rain-1.png",
                "max": 31,
                "min": 24
            }
        ]
    }
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | JSON\_PARSING\_ERROR | api의 잘못된 응답으로 인한 json 문서 파싱 에러 |
| 500 | UNKNOWN\_ERROR | 이 외 |

