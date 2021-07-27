---
description: 시간대별 강수량을 알려주는 api
---

# 시간대별 날씨 페이지

## 1\) URL

```text
GET /weather/time
```

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code: `200 OK`

### Description

![](https://user-images.githubusercontent.com/68107000/124440085-31d82500-ddb5-11eb-9a1e-b9cc888a4380.png)

* tempInfo
  * tempInfo.resultCode: 응답 코드
  * tempInfo.errorMessage: 에러 메세지 \(성공 시 SUCCESS 반환\)
  * tempInfo.document
    * tempInfo.document.time:  시간
    * tempInfo.document.temperature: 기온
    * tempInfo.document.icon: 날씨 icon URL

![](https://user-images.githubusercontent.com/68107000/124441433-a19adf80-ddb6-11eb-9d14-9d8736b524ba.png)

* rainInfo
  * rainInfo.resultCode: 응답 코드
  * rainInfo.errorMessage: 에러 메세지 \(성공 시 SUCCESS 반환\)
  * rainInfo.document
    * rainInfo.document.time: 시간
    * rainInfo.document.rain: 강수량
    * rainInfo.document.percent: 강수 확률
    * rainInfo.document.icon: 물방울 icon URL

![](https://user-images.githubusercontent.com/68107000/126878184-4b724c1d-025c-4aef-9844-b02681fcc3ae.png)

* ootdInfo
  * ootdInfo.resultCode: 응답 코드
  * ootdInfo.errorMessage: 에러 메세지 \(성공 시 SUCCESS 반환\)
  * ootdInfo.document
    * ootdInfo.document.umbrellaIcon: 우산 icon URL
    * ootdInfo.document.umbrellaFlag: 우산 안내에 대한 flag
    * ootdInfo.document.clothes
      * ootdInfo.document.clothes.age: 물방울 icon URL
      * ootdInfo.document.clothes.top: 상의 icon URL
      * ootdInfo.document.clothes.bottom: 하의 icon URL
      * ootdInfo.document.clothes.shoes: 신발 icon URL
      * ootdInfo.document.clothes.desc: 아이템 설명 // 난해
      * ootdInfo.document.clothes.reason: 추천 이유 // 난해

### Example

```javascript
{
    "tempInfo": {
        "resultCode": 200,
        "errorMessage": "SUCCESS",
        "document": [
            {
                "time": "현재",
                "temperature": "25°",
                "icon": "png60.png"
            },
            {
                "time": "18시",
                "temperature": "24°",
                "icon": "png60.png"
            },
            {
                "time": "19시",
                "temperature": "23°",
                "icon": "png60.png"
            },
            {
                "time": "20시",
                "temperature": "22°",
                "icon": "png60.png"
            }
        ]
    },
    "rainInfo": {
        "resultCode": 200,
        "errorMessage": "SUCCESS",
        "document": [
            {
                "time": "현재",
                "rain": 0,
                "percent": 0,
                "icon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/rain/0.png"
            },
            {
                "time": "18시",
                "rain": 30,
                "percent": 60,
                "icon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/rain/60.png"
            },
            {
                "time": "19시",
                "rain": 40,
                "percent": 90,
                "icon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/rain/90.png"
            },
            {
                "time": "20시",
                "rain": 10,
                "percent": 10,
                "icon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/rain/10.png"
            }
        ]
    },
    "ootdInfo": {
        "resultCode": 200,
        "errorMessage": "SUCCESS",
        "document": {
            "umbrellaIcon": "umbrella.png",
            "umbrellaFlag": true,
            "clothes": {
                "age": 20,
                "top": "top.png",
                "bottom": "bottom.png",
                "shoes": "shoes.png"
                "desc": "아이템 설명",
                "reason": "추천 이유"
            }
        }
    }
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

