---
description: 전국 확진자 수와 지역 확진자 수를 알려주는 api
---

# 메인 페이지

## 1\) URL

```text
GET /covid/main
```

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
	"location": "계양구 병방동",
	"coronic_total": 567,
	"coronic_region": 334,
	"comp_total": 128,
	"comp_region": 8,
	"is_inc_total": 1,
	"is_inc_region": -1
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

