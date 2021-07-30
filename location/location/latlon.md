---
description: '위경도의 읍면동, 행정구역코드 정보를 반환하는 api'
---

# 위경도에서 변환

## 1\) URL

### Request URL

```text
GET /location/latlon
```

### Request Parameter

| parameter | requirement | description |
| :---: | :---: | :---: |
| lat | Y\(필수\) | 위도 |
| lon | Y\(필수\) | 경도 |

```markup
/location/latlon?lat=37.12435&lon=127.48921
```

## 2\) RESPONSE BODY

### Success http status code

`200 OK`

### Description

* res: 정보가 응답되었는지에 대한 flag
* umd: 읍면동
* addressCode: 행정구역코드

### Example

```typescript
{
    "res": true,
    "umd": "일죽면",
    "addressCode": "4155039032"
}
```

## 3\) Error

### Example

정보가 없거나 데이터베이스 통신 에러가 발생한 경우

```java
{
    "res": false,
    "umd": null,
    "addressCode": null
}
```

