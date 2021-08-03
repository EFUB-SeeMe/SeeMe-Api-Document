---
description: "미세먼지, 통합 대기질, 마스크 추천 정보를 반환하는 api\U0001F60A"
---

# 메인 페이지

## 1\) URL

### Request URL

```text
GET /microdust/main
```

\* 요청 파라미터가 없을 때, 서울특별시 용산구 이촌동의 값을 보여줍니다.

### Request Parameter1

| parameter | requirement | description |
| :---: | :---: | :--- |
| lat | N | 위도 |
| lon | N | 경도 |

```text
GET /microdust/main?lat=37.5145963013281&lon=126.9754626313914
```

### Request Parameter 2

| parameter | requirement | description |
| :---: | :---: | :--- |
| code | N | 행정 구역 코드 |

```text
GET /microdust/main?code=2824510700
```

\* 검색 시 해당 파라미터를 이용하여 호출할 수 있습니다.

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code: `200 OK`

### Description

**main document**

![image](https://user-images.githubusercontent.com/68107000/127577262-0a6ac7e3-3e87-48e5-90f9-e8cb8b30ecb6.png)

| name | type | description |
| :---: | :---: | :--- |
| grade | string | 현재 미세먼지 등급 좋음, 보통, 나쁨, 매우나쁨 의 값을 나타냄 |
| gradeIcon | string | 아이콘 이미지 URL |
| pm10Flag | boolean | 미세먼지 농도 값 유무 |
| pm25Flag | boolean | 초미세먼지 농도 값 유무 |
| pm10 | int | 현재 미세먼지 농도 |
| pm25 | int | 현재 초미세먼지 농도 |
| desc | string | 설명 |

**total document**

![image](https://user-images.githubusercontent.com/68107000/127577218-b26095f1-2d57-43cf-8818-fb0e821b7f46.png)

| name | type | description |
| :---: | :---: | :--- |
| so2Flag | boolean | 아황산가스 농도 값 유무 |
| coFlag  | boolean | 일산화탄소 농도 값 유무 |
| o3Flag  | boolean | 오존 농도 값 유무       |
| no2Flag | boolean | 이산화질소 농도 값 유무 |
|   so2   | double  | 아황산가스 농도         |
|   co    | double  | 일산화탄소 농도         |
|   o3    | double  | 오존 농도               |
|   no2   | double  | 이산화질소 농도 |

**mask document**

![image](https://user-images.githubusercontent.com/68107000/127577301-f9e01dc6-0965-4b69-a469-5b996b7a3e46.png)

| name | type | description |
| :---: | :---: | :--- |
| maskIcon | string | 마스크 아이콘 URL |
| desc | string | 마스크 추천 |

### Example

```java
{
    "mainInfo": {
        "resultCode": 200,
        "errorMessage": "SUCCESS",
        "document": {
            "grade": "보통",
            "gradeIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/microdust/pm/soso.png",
            "pm10Flag": true,
            "pm25Flag": true,
            "pm10": 29,
            "pm25": 17,
            "desc": "적당한 야외 활동은 괜찮아요 ~"
        }
    },
    "totalInfo": {
        "resultCode": 200,
        "errorMessage": "SUCCESS",
        "document": {
            "so2Flag": true,
            "coFlag": true,
            "o3Flag": true,
            "no2Flag": true,
            "caiFlag": true,
            "so2": 0.003,
            "co": 0.4,
            "o3": 0.009,
            "no2": 0.032,
            "cai": 54.0,
            "caiIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/microdust/cai/soso.png"
        }
    },
    "maskInfo": {
        "resultCode": 200,
        "errorMessage": null,
        "document": {
            "maskIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/mask/kf80.png",
            "desc": "미세먼지가 꽤 있어요 ㅠㅠ kf80 추천!"
        }
    }
}
```

## 3\) ERROR CODE

| error code | error message | description |
| :---: | :---: | :--- |
| 500 | API\_PROVISION\_ERROR | API 제공사의 문제 |
| 500 | JSON\_PARSING\_ERROR | json 파싱 과정에서의 문제 |
| 500 | UNKNOWN\_ERROR | 이 외 |

### Example

```java
{
    "mainInfo": {
        "resultCode": 500,
        "errorMessage": "API_PROVISION_ERROR",
        "document": null
    },
    "totalInfo": {
        "resultCode": 200,
        "errorMessage": "API_PROVISION_ERROR",
        "document": null
    },
    "maskInfo": {
        "resultCode": 200,
        "errorMessage": "API_PROVISION_ERROR",
        "document": null
    }
}
```

