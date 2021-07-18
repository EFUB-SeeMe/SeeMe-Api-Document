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

| name | type | description |
| :--- | :--- | :--- |
| station_name | string | 측정소 이름 |
| lat          | double | 위도                                                        |
| lon          | double | 경도                                                        |
| pm10         | int | 미세먼지 농도                                               |
| pm25         | int    | 초미세먼지 농도                                             |
| grade        | int    | 등급 - 색상구분<br />1: 좋음, 2: 보통, 3: 나쁨, 4: 매우나쁨 |

### Example

```java
{
    [
        {
            "station_name" : "계산",
            "lat": 37.1034324,
            "lon": 127.3149832,
            "pm10": 10,
            "pm25": 11,
            "grade": 1
        }, 
        {
            "station_name" : "삼산", 
            "lat": 37.1034324,
            "lon": 127.3149832,
            "pm10": 10,
            "pm25": 11,
            "grade": 1
        }, 
        { 
            "station_name" : "", // 이후의 값은 임의의 값임
            "lat": "",
            "lon": "",
            "pm10": 10,
            "pm25": 11,
            "grade": 1
        }, 
        {
            "station_name" : "",
            "lat": "",
            "lon": "",
            "pm10": 10,
            "pm25": 11,
            "grade": 1
        }, 
        {
            "station_name" : "",
            "lat": "",
            "lon": "",
            "pm10": 10,
            "pm25": 11,
            "grade": 1
        }, 
    ]
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

