---
description: 전국 확진자 수와 지역 확진자 수를 알려주는 api
---

# 메인 페이지

## 1\) URL

### Request URL

```text
GET /covid/main
```

### Request Parameter 1

| parameter | requirement | description |
| :-------: | :---------: | ----------- |
|    lat    |      N      | 위도        |
|    lon    |      N      | 경도        |

```
GET /covid/main?lat=37.47161263526149&lon=126.71495060184574
```

\* lat 또는 lon 둘 중 하나라도 값이 없는 경우에는, 서울 지역의 값을 보여줍니다.

### Request Parameter 2

| parameter | requirement | description | available value                                              |
| :-------: | :---------: | ----------- | ------------------------------------------------------------ |
| location  |      N      | 지역 이름   | 서울, 인천, 경기, 제주, 경남, 경북, 전남, 전북, 충남, 충북, 강원, 세종, 울산, 대전, 광주, 대구, 부산 |

```
GET /covid/main?location=서울
```

\* 검색 시 해당 파라미터를 이용하여 호출할 수 있습니다.

\* "줄임말이 아닌 인천광역시, 세종특별자치시 와 같은 본래의 이름으로 호출하고 싶다" 등 의견 주시면 반영하겠습니다 !

## 2\) RESPONSE BODY

### Success http status code

 `200 OK`

### Description

![image](https://user-images.githubusercontent.com/68107000/124694390-22272080-df1c-11eb-9ba6-d0c451b05455.png)

| name | type | description |
| :---: | :---: | :---- |
| location | string | 현재 위치 |
| coronic\_total | unsigned int | 전국 확진자 수 |
| coronic\_region | unsigned int | 지역 확진자 수 |
| comp\_total | unsigned int | 전국 확진자 수 전날 대비 변화량 |
| comp\_region | unsigned int | 지역 확진자 수 전날 대비 변화량 |
| is\_inc_total | int | 전국, 전날 대비 증감 표현<br />-1: 감소, 0: 동일, 1: 증가 |
| is\_inc_region | int | 지역, 전날 대비 증감 표현<br />-1: 감소, 0: 동일, 1: 증가 |

### Example

```json
{
  "location": "인천",
  "coronicTotal": 1316,
  "coronicRegion": 82,
  "compTotal": 41,
  "compRegion": 18,
  "isIncTotal": -1,
  "isIncRegion": -1
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

