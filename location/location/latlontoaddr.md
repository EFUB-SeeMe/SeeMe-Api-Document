---
description: 위도와 경도를 입력받아 읍면동까지의 주소로 반환하는 api
---

# 위경도→주소

## 1\) URL

### Request URL

```text
GET /location/latlon2address
```

### Request Parameter

| parameter | requirement | description |
| :---: | :---: | :---: |
| lat | Y\(필수\) | 위도 |
| lon | Y\(필수\) | 경도  |

```text
/location/latlon2address?lat=37.12335&lon=127.23412
```

## 2\) RESPONSE BODY

### Success http status code

`200 OK`

### Description

| name | type | description |
| :---: | :---: | :---: |
| address | string | 주소 |

### Example

```markup
용인시 처인구 이동읍
```

## 3\) ERROR

### Example

정보가 없거나 json 파싱 과정에서 에러가 발생한 경우

```
지원하지 않는 위치입니다.
```

