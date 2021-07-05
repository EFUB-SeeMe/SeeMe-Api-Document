---
description: 전국 확진자 수와 지역 확진자수를 알려주는 api
---

# 메인 페이지

## 1\) URL

```text
GET /covid/main
```

## 2\) RESPONSE BODY

### Suceess http status code

HTTP Status code: `200 OK`

### Description

| name | type | description |
| :---: | :---: | :---: |
| location | string | 현재 위 |
| coronic\_total | unsigned int | 전국 확진자 수 |
| coronic\_region | unsigned int | 지역 확진자 |
| comp\_coronic\_total | unsigned int | 전날 대비 전국 확진자 |
| comp\_coronic\_total | unsigned int | 전날 대비 지역 확진자 |
| is\_inc | boolean | 전날 대비 증감 |

### Example

```yaml
{
	"location": "계양구 병방동",
	"coronic_total": 567,
	"coronic_region": 334,
	"comp_coronic_total": 128,
	"comp_coronic_region": 8,
	"is_inc": true
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에 |



