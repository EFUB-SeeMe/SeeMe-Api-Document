---
description: 지도를 통해 현재 미세먼지 및 초미세먼지 농도를 알려주는 API
---

# 도시별 농도 페이지

## 1\) URL

```text
GET /microdust/map
```

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code : `200 OK`

### Description

![image](https://user-images.githubusercontent.com/68282057/124726872-1ef65980-df49-11eb-8139-976b5783d790.png)

| name | type | description | etc |
| :--- | :--- | :--- | :--- |
| station\_name | string | 측정소 이름 | 고유한 값 \(유일한 값\), 현재 총 600개 |
| lat | double | 위도 | 소수점 최대 7자리 |
| lon | double | 경도 | 소수점 최대 7자리 |
| pm10 | string | 미세먼지 농도 | 측정 이상의 경우, "-" 측정 이상이 아주 드묾 |
| pm25 | string | 초미세먼지 농도 | 측정 이상의 경우, "-" 측정 이상이 빈번함 |
| grade | string | 등급 - 색상구분 | 1: 좋음, 2: 보통, 3: 나쁨, 4: 매우나쁨 측정 이상의 경우, null |

### Example

```java
[
    {
        "stationName": "청룡동",
        "lat": 35.274045,
        "lon": 129.090793,
        "pm10": "13",
        "pm25": "4",
        "grade": "1"
    },
    {
        "stationName": "좌동",
        "lat": 35.1708927,
        "lon": 129.1741659,
        "pm10": "20",
        "pm25": "6",
        "grade": "1"
    },
    {
        "stationName": "재송동",
        "lat": 35.182668,
        "lon": 129.118136,
        "pm10": "15",
        "pm25": "8",
        "grade": "1"
    },
    {
        "stationName": "장림동",
        "lat": 35.08298,
        "lon": 128.9667622,
        "pm10": "27",
        "pm25": "14",
        "grade": "1"
    },
    {
        "stationName": "대저동",
        "lat": 35.20958,
        "lon": 128.9713671,
        "pm10": "-",
        "pm25": "-",
        "grade": null
    },
    // 이렇게 600개의 측정소의 데이터가 보내집니다.
]
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

