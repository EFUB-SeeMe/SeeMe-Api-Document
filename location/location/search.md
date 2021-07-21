---
description: 읍면동 주소를 행정구역코드로 변환하여 서비스를 호출하기 위한 api
---

# 읍면동→행정구역코드

## 1\) URL

### Request URL

```text
http://localhost:8080/location/search
```

### Request Parameter

| parameter | requirement | description |
| :---: | :---: | :---: |
| umd | Y\(필수\) | 읍면동 이름 |

```yaml
http://localhost:8080/location/search?umd=남산동
```

## 2\) RESPONSE BODY

### Success http status code

`200 OK`

### Description

| name | type | description |
| :---: | :---: | :---: |
| totalCount | int | 검색한 읍면동이 포함된 주소의 개수 |
| addressList | `addr_list` | 검색한 읍면동이 포함된 주소 목록 |

\* `addr_list`

| name | type | description |
| :---: | :---: | :---: |
| address | string | 주소 |
| addressCode | string | 행정구역코드 |

### Example

```yaml
{
  "totalCount": 4,
  "addressList": [
    {
      "address": "부산광역시 금정구 남산동",
      "addressCode": "2641010400"
    },
    {
      "address": "대구광역시 중구 남산동",
      "addressCode": "2711015600"
    },
    {
      "address": "광주광역시 광산구 남산동",
      "addressCode": "2920016700"
    },
    {
      "address": "전라남도 여수시 남산동",
      "addressCode": "4613011600"
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

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 400 | BAD\_REQUEST | 잘못된 요청 |

