---
description: "코로나 페이지 관련 API 입니다\U0001F609"
---

# 코로나 페이지

/main

| name | type | description |
| :---: | :---: | :---: |
| location | string | 현재 위치 |
| coronic\_total | unsigned int | 전국 확진자 수 |
| coronic\_region | unsigned int | 지역 확진자 수 |
| comp\_coronic\_total | unsigned int | 전날 대비 전국 확진자 수 |
| comp\_coronic\_region | unsigned int | 전날 대비 지역 확진자 수 |
| is\_inc | boolean | 전날 대비 증감 여부 |

/national

| name | type | description |
| :---: | :---: | :---: |
| new | unsigned int | 신규 확진자 수 |
| total | unsigned int | 누적 확진자 수 |
| graph | list | 확진자 추이 그래프 |
| day | string | 날짜 |
| coronic | unsigned int | 요일별 확진자 수 |

/region

| name | type | description |
| :---: | :---: | :---: |
| new | unsigned int | 신규 확진자 수 |
| total | unsigned int | 누적 확진자 수 |
| graph | list | 확진자 추이 그래프 |
| day | string | 날짜 |
| coronic | unsigned int | 요일별 확진자 수 |

