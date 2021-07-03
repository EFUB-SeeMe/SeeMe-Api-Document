---
이번주 날씨를 알려주는 api
---

# 이번주 날씨 페이지

## URL

```
GET /weather/weekly
```



## RESPONSE BODY

### Description

| name    | type   | description                     |
| ------- | ------ | ------------------------------- |
| day     | string | 날짜, 1월 1일 (월) 과 같은 형식 |
| am_rain | int    | 오전 강수 확률                  |
| am_icon | string | 오전 날씨 아이콘 URL            |
| pm_rain | int    | 오후 강수 확률                  |
| pm_icon | string | 오후 날씨 아이콘 URL            |
| max     | int    | 최고 온도                       |
| min     | int    | 최저 온도                       |

### Example

```json
{
	[
		{
            "day": "6월 28일(월)",
            "am_rain": 30,
            "am_icon": "~~~.png",
            "pm_rain": 10,
            "pm_icon": "~~~.png",
            "max": 29,
            "min": 21
        },
		{
            "day": "6월 29일 (화)",
            "am_rain": 30,
            "am_icon": "~~~.png",
            "pm_rain": 10,
            "pm_icon": "~~~.png",
            "max": 29,
            "min": 21
        },
        {
            "day": "6월 30일 (수)",
            "am_rain": 30,
            "am_icon": "~~~.png",
            "pm_rain": 10,
            "pm_icon": "~~~.png",
            "max": 29,
            "min": 21
        },
        {
            "day": "7월 1일 (목)",
            "am_rain": 30,
            "am_icon": "~~~.png",
            "pm_rain": 10,
            "pm_icon": "~~~.png",
            "max": 29,
            "min": 21
        },
        {
            "day": "7월 2일 (금)",
            "am_rain": 30,
            "am_icon": "~~~.png",
            "pm_rain": 10,
            "pm_icon": "~~~.png",
            "max": 29,
            "min": 21
        },
        {
            "day": "7월 3일 (토)",
            "am_rain": 30,
            "am_icon": "~~~.png",
            "pm_rain": 10,
            "pm_icon": "~~~.png",
            "max": 29,
            "min": 21
        },
    	{
            "day": "7월 4일 (일)",
            "am_rain": 30,
            "am_icon": "~~~.png",
            "pm_rain": 10,
            "pm_icon": "~~~.png",
            "max": 29,
            "min": 21
        },
    ]
}
```

## ERROR CODE

| error code | error message         | description    |
| ---------- | --------------------- | -------------- |
| 500        | INTERNAL_SERVER_ERROR | 서버 내부 에러 |

