---
description: 전국 확진자 추이를 알려주는 api
---

# 전국 확진자 추이 페이지

## 1\) URL

```text
GET /covid/national
```

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code: `200 OK`

### Description

| name | type | description |
| :---: | :---: | :---: |
| new | unsigned int | 신규 확진자 수 |
| total | unsigned int | 누적 확진자 수 |
| graph | list | 확진자 추이 그래프 |
| day | string | 날짜 |
| coronic | unsigned int | 요일별 확진자 수 |

### Example

```yaml
{
	"new": 334
	"total": 157723
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
				"day": "현재",
				"coronic": 205
			}
		]
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :--- | :--- | :--- |
| 500 | INTERNAL\_SERVER\_ERROR | 서버 내부 에러 |

