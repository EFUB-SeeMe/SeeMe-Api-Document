---
description: 지역 확진자 수 추이를 알려주는 api
---

# 지역 확진자 추이 페이지

## 1\) URL

### Request URL

```text
GET /covid/regional
```

### Request Parameter 1

| parameter | requirement | description |
| :---: | :---: | :--- |
| lat | N | 위도 |
| lon | N | 경도 |

```text
GET /covid/regional?lat=37.47161263526149&lon=126.71495060184574
```

\* lat 또는 lon 둘 중 하나라도 값이 없는 경우에는, 서울 지역의 값을 보여줍니다.

### Request Parameter 2

| parameter | requirement | description | available value |
| :---: | :---: | :--- | :--- |
| location | N | 지역 이름 | 서울, 인천, 경기, 제주, 경남, 경북, 전남, 전북, 충남, 충북, 강원, 세종, 울산, 대전, 광주, 대구, 부산 |

```text
GET /covid/regional?location=서울
```

\* 검색 시 해당 파라미터를 이용하여 호출할 수 있습니다.

\* "줄임말이 아닌 인천광역시, 세종특별자치시 와 같은 본래의 이름으로 호출하고 싶다" 등 의견 주시면 반영하겠습니다 !

## 2\) RESPONSE BODY

### Success http status code

`200 OK`

### Description

![image](https://user-images.githubusercontent.com/68107000/124695165-a62dd800-df1d-11eb-92a5-73e2a7613a0d.png)

| name | type | description |
| :---: | :---: | :--- |
| newCoronic | unsigned int | 신규 확진자 수 |
| totalCoronic | unsigned int | 누적 확진자 수 |
| graph | `coronic_list` | 확진자 추이 그래프 |

* `coronic_list`
* | name | type | description |
  | :---: | :---: | :--- |
  | day | string | 날짜 |
  | coronic | unsigned int | 요일별 확진자 수 |

### Example

```yaml
{
    "newCoronic": 334
    "totalCoronic": 157723
    "graph" :
        [
            {
                "day": "06.23",
                "coronic": 269
            },
            {
                "day": "06.24",
                "coronic": 242
            },
            {
                "day": "06.25",
                "coronic": 185
            },
            {
                "day": "06.26",
                "coronic": 185
            },
            {
                "day": "06.27",
                "coronic": 205
            }
        ]
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

