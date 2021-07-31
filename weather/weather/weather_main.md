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

![](https://user-images.githubusercontent.com/68107000/126878184-4b724c1d-025c-4aef-9844-b02681fcc3ae.png)

* ootdInfo
  * ootdInfo.resultCode: 응답 코드 \(200 = SUCCESS, 500 = ERROR\)
  * ootdInfo.errorMessage: 에러 메세지 \(성공 시 SUCCESS 반환\)
  * ootdInfo.document
    * ootdInfo.document.age10
    * ootdInfo.document.age20
    * ootdInfo.document.age30
    * ootdInfo.document.age40
    * ootdInfo.document.age50
      * ootdInfo.document.age50.item1: 상의 icon URL
      * ootdInfo.document.age50.item1Desc: 상의 icon 설명
      * ootdInfo.document.age50.item2: 하의 icon URL
      * ootdInfo.document.age50.item2Desc: 하의 icon 설명
      * ootdInfo.document.age50.item3: 신발 icon URL
      * ootdInfo.document.age50.item3Desc: 신발 icon 설명
      * ootdInfo.document.age50.item4: 기타 icon URL(rainFlag가 true이면 우산 아이템 추천)
      * ootdInfo.document.age50.item4Desc: 기타 icon URL

### Example

```javascript
{
  "currentInfo": {
    "resultCode": 200,
    "errorMessage": "SUCCESS",
    "document": {
      "currTemp": 25,
      "feelTemp": 27,
      "iconDesc": "흐림",
      "icon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Cloud.png",
      "comp": "오늘은 어제보다 1도 낮습니다."
    }
  },
  "minmaxInfo": {
    "resultCode": 200,
    "errorMessage": "SUCCESS",
    "document": {
      "min": 25,
      "max": 34,
      "desc": "따뜻하고 점차 흐려짐; 밤 늦게 때때로 소나기가 내림"
    }
  },
  "ootdInfo": {
    "resultCode": 200,
    "errorMessage": "SUCCESS",
    "document": {
      "age10": {
        "item1": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/55.png",
        "item1Desc": "반팔 티셔츠",
        "item2": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/56.png",
        "item2Desc": "트레이닝 바지",
        "item3": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/57.png",
        "item3Desc": "스니커즈",
        "item4": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/58.png",
        "item4Desc": "캡모자"
      },
      "age20": {
        "item1": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/60.png",
        "item1Desc": "반팔 티셔츠",
        "item2": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/65.png",
        "item2Desc": "여름용 조거팬츠",
        "item3": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/66.png",
        "item3Desc": "슬리퍼",
        "item4": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/67.png",
        "item4Desc": "부채"
      },
      "age30": {
        "item1": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/68.png",
        "item1Desc": "스트라이프 셔츠",
        "item2": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/69.png",
        "item2Desc": "슬랙스",
        "item3": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/70.png",
        "item3Desc": "로퍼",
        "item4": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/71.png",
        "item4Desc": "미니선풍기"
      },
      "age40": {
        "item1": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/72.png",
        "item1Desc": "얇은 셔츠",
        "item2": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/73.png",
        "item2Desc": "슬랙스",
        "item3": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/74.png",
        "item3Desc": "로퍼",
        "item4": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/75.png",
        "item4Desc": "여름용 양산"
      },
      "age50": {
        "item1": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/76.png",
        "item1Desc": "반팔 셔츠",
        "item2": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/77.png",
        "item2Desc": "인견 바지",
        "item3": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/78.png",
        "item3Desc": "샌들",
        "item4": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/clothes/79.png",
        "item4Desc": "여름용 양산"
      }
    }
  },
  "weekInfo": {
    "resultCode": 200,
    "errorMessage": "SUCCESS",
    "document": [
      {
        "day": "07월31일 (토)",
        "amRain": 0,
        "amRainPercent": 15,
        "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Sun.png",
        "pmRain": 0,
        "pmRainPercent": 42,
        "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Rain-2.png",
        "max": 34,
        "min": 25
      },
      {
        "day": "08월01일 (일)",
        "amRain": 2,
        "amRainPercent": 60,
        "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Rain-1.png",
        "pmRain": 1,
        "pmRainPercent": 40,
        "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Rain-1.png",
        "max": 29,
        "min": 23
      },
      {
        "day": "08월02일 (월)",
        "amRain": 12,
        "amRainPercent": 69,
        "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Rain-1.png",
        "pmRain": 8,
        "pmRainPercent": 59,
        "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Rain-1.png",
        "max": 30,
        "min": 24
      },
      {
        "day": "08월03일 (화)",
        "amRain": 0,
        "amRainPercent": 41,
        "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Sun.png",
        "pmRain": 0,
        "pmRainPercent": 25,
        "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Moon.png",
        "max": 32,
        "min": 24
      },
      {
        "day": "08월04일 (수)",
        "amRain": 1,
        "amRainPercent": 59,
        "amIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Sun.png",
        "pmRain": 1,
        "pmRainPercent": 51,
        "pmIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Moon.png",
        "max": 33,
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

