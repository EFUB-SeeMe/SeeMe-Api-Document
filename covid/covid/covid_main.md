---
description: 전국 확진자 수와 지역 확진자 수를 알려주는 api
---

# 메인 페이지

## 1\) URL

### Request URL

```text
GET /covid/main
```

\* 요청 파라미터가 없을 때, 서울 지역의 값을 보여줍니다.

### Request Parameter 1

| parameter | requirement | description |
| :---: | :---: | :--- |
| lat | N | 위도 |
| lon | N | 경도 |

```text
GET /covid/main?lat=37.47161263526149&lon=126.71495060184574
```

### Request Parameter 2

| parameter | requirement | description | available value |
| :---: | :---: | :--- | :--- |
| location | N | 지역 이름 | 서울, 인천, 경기, 제주, 경남, 경북, 전남, 전북, 충남, 충북, 강원, 세종, 울산, 대전, 광주, 대구, 부산 |

```text
GET /covid/main?location=서울
```

\* 검색 시 해당 파라미터를 이용하여 호출할 수 있습니다.

## 2\) RESPONSE BODY

### Success http status code

`200 OK`

### Description

![image](https://user-images.githubusercontent.com/68107000/124694390-22272080-df1c-11eb-9ba6-d0c451b05455.png)

| name | type | description |
| :---: | :---: | :--- |
| location | string | 현재 위치 |
| coronicTotal | int | 전국 확진자 수 |
| coronicRegion | int | 지역 확진자 수 |
| compTotal | int | 전국 확진자 수 전날 대비 변화량 |
| compRegion | int | 지역 확진자 수 전날 대비 변화량 |
| isIncTotal | int | 전국, 전날 대비 증감 표현 -1: 감소, 0: 동일, 1: 증가 |
| isIncRegion | int | 지역, 전날 대비 증감 표현 -1: 감소, 0: 동일, 1: 증가 |

### Example

```javascript
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

