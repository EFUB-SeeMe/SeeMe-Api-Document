---
description: 읍면동 주소를 행정구역코드로 변환하여 서비스를 호출하기 위한 api
---

# 읍면동에서 변환

## 1\) URL

### Request URL

```text
GET /location/umd
```

### Request Parameter

| parameter | requirement | description |
| :---: | :---: | :---: |
| umd | Y\(필수\) | 읍면동 이름 |

```yaml
/location/umd?umd=남산동
```

## 2\) RESPONSE BODY

### Success http status code

`200 OK`

### Description

- totalCount: 검색된 주소 개수
- addressList: 검색한 읍면동이 포함된 주소 목록
  - addressList.sidoShort: 2자리 축약된 형태의 시도
  - addressList.address: 주소
  - addressList.addressCode: 행정구역코드
  - addressList.lat: 위도
  - addressList.lon: 경도

### Example

```yaml
{
    "totalCount": 7,
    "addressList": [
        {
            "sidoShort": "부산",
            "address": "부산광역시 금정구 남산동",
            "addressCode": "2641010400",
            "lat": 35.271656,
            "lon": 129.09225
        },
        {
            "sidoShort": "대구",
            "address": "대구광역시 중구 남산동",
            "addressCode": "2711015600",
            "lat": 35.859386,
            "lon": 128.59044
        },
        {
            "sidoShort": "광주",
            "address": "광주광역시 광산구 남산동",
            "addressCode": "2920016700",
            "lat": 35.176586,
            "lon": 126.72587
        },
        {
            "sidoShort": "전남",
            "address": "전라남도 여수시 남산동",
            "addressCode": "4613011600",
            "lat": 34.735046,
            "lon": 127.730156
        },
        {
            "sidoShort": "경북",
            "address": "경상북도 경주시 남산동",
            "addressCode": "4713012000",
            "lat": 35.79093,
            "lon": 129.24063
        },
        {
            "sidoShort": "경북",
            "address": "경상북도 김천시 남산동",
            "addressCode": "4715010600",
            "lat": 36.115646,
            "lon": 128.11455
        },
        {
            "sidoShort": "경남",
            "address": "경상남도 창원시 남산동",
            "addressCode": "4812310600",
            "lat": 35.19829,
            "lon": 128.69577
        }
    ]
}
```

\* 검색 결과가 없는 경우: totalCount 값이 0, addressList 요소 없는 상태로 반환

```yaml
{
    "totalCount": 0,
    "addressList": [

    ]
}
```

