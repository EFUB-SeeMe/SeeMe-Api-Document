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

![](https://user-images.githubusercontent.com/68107000/124440780-f427cc00-ddb5-11eb-859f-a3d9d53492eb.png)

* resultCode: 응답 코드 \(≠ status code, =서버가 자체적으로 만든 코드, 추후 error code에 정리\)
* errorMessage: 에러 메세지 \(성공 시 SUCCESS 반환\)
* document
  * document.icon:  아이콘 URL
  * document.iconDesc: 아이콘 설명
  * document.currTemp: 현재 온도
  * document.feelTemp: 체감 온도
  * document.max: 최고 온도
  * document.min: 최저 온도
  * document.desc: 오늘 날씨에 대한 설명
  * document.comp: 전날과의 비교설명

### Example

```javascript
{
    "resultCode": 200,
    "errorMessage": "SUCCESS",
    "document": {
        "icon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/weather/Sun.png",
        "iconDesc": "맑음",
        "currTemp": 26,
        "feelTemp": 28,
        "max": 29,
        "min": 20,
        "desc": "오늘은 초복이에요! 기력을 보충해보는 건 어떨까요?",
        "comp": "오늘은 어제와 비슷한 날씨가 예상됩니다."
    }
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
|  | JSON\_PARSING\_ERROR | api의 잘못된 응답으로 인한 json 문서 파싱 에러 |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

