---
description: "미세먼지 페이지 관련 API입니다\U0001F60A"
---

# 메인 페이지

## 1\) URL

### Request URL

```text
GET /microdust/main
```

### Request Parameter1

| parameter | requirement | description |
| :---: | :---: | :--- |
| lat | N | 위도 |
| lon | N | 경도 |

```text
GET /microdust/main?lat=37.5145963013281&lon=126.9754626313914
```

\* lat 또는 lon 둘 중 하나라도 값이 없는 경우에는, 서울특별시 용산구 이촌동의 값을 보여줍니다.

### Request Parameter 2

| parameter | requirement | description |
| :---: | :---: | :--- |
| code | N | 행정동코드 |

```text
GET /microdust/main?code=2824510700
```

\* 검색 시 해당 파라미터를 이용하여 호출할 수 있습니다.

## 2\) RESPONSE BODY

### Success http status code

HTTP Status code: `200 OK`

### Description

![main](../../.gitbook/assets/.png%20%281%29.png)

![rec](../../.gitbook/assets/.png%20%282%29.png)

<table>
  <thead>
    <tr>
      <th style="text-align:center">name</th>
      <th style="text-align:center">type</th>
      <th style="text-align:center">description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:center">resultCode</td>
      <td style="text-align:center">int</td>
      <td style="text-align:center">&#xC0C1;&#xD0DC; &#xCF54;&#xB4DC;</td>
    </tr>
    <tr>
      <td style="text-align:center">errorMessage</td>
      <td style="text-align:center">string</td>
      <td style="text-align:center">
        <p>&#xC5D0;&#xB7EC; &#xBC1C;&#xC0DD; &#xC6D0;&#xC778;</p>
        <p>&#xC5D0;&#xB7EC;&#xAC00; &#xBC1C;&#xC0DD;&#xD558;&#xC9C0; &#xC54A;&#xC558;&#xB2E4;&#xBA74;
          null</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:center">response</td>
      <td style="text-align:center">string</td>
      <td style="text-align:center">&#xCEF4;&#xD3EC;&#xB10C;&#xD2B8; &#xC774;&#xB984;</td>
    </tr>
    <tr>
      <td style="text-align:center">document</td>
      <td style="text-align:center">object</td>
      <td style="text-align:center">&#xAC01; &#xCEF4;&#xD3EC;&#xB10C;&#xD2B8;&#xC758; &#xAC1D;&#xCCB4;</td>
    </tr>
  </tbody>
</table>

\* resultCode : 값이 잘 호출이 되었는지를 알려주는 코드입니다. 

* 200: 에러 없이 값이 잘 호출되었음

\* document : 밑의 각 컴포넌트별 document 참고

### **main document**

| name | type | description |
| :---: | :---: | :---: |
| grade | string | 현재 미세먼지 등급 좋음, 보통, 나쁨, 매우나쁨 의 값을 나타냄 |
| gradeIcon | string | 아이콘 이미지 URL |
| pm10Flag | boolean | 미세먼지 농도 값 유무 |
| pm25Flag | boolean | 초미세먼지 농도 값 유무 |
| pm10 | int | 현재 미세먼지 농도 |
| pm25 | int | 현재 초미세먼지 농도 |
| desc | string | 설명 |

### other document

| name | type | description |
| :---: | :---: | :--- |
| pm10Flag | boolean | 미세먼지 농도 값 유무 |
| pm25Flag | boolean | 초미세먼지 농도 값 유무 |
| so2Flag | boolean | 아황산가스 농도 값 유무 |
| coFlag | boolean | 일산화탄소 농도 값 유무 |
| o3Flag | boolean | 오존 농도 값 유무 |
| no2Flag | boolean | 이산화질소 농도 값 유무 |
| pm10 | double | 미세먼지 농도 |
| pm25 | double | 초미세먼지 농도 |
| so2 | double | 아황산가스 농도 |
| co | double | 일산화탄소 농도 |
| o3 | double | 오존 농도 |
| no2 | double | 이산화질소 농도 |

### rec document

| name | type | description |
| :---: | :---: | :---: |
| maskIcon | string | 마스크 아이콘 URL  |
| desc | string | 마스크 추천  |
| cai | double | 통합대기환경지수 |
| caiFlag | boolean | 통합대기환경지수 값 유무 |

\* CAI\(통합대기환경지수\): 미세먼지\(PM10\), 초미세먼지\(PM2.5\), 이산화질소\(NO2\), 오존\(O3\) 이 모두 입력될 경우에만 CAI 산정이 가능합니다.

→ 미세먼지, 초미세먼지, 이산화질소, 오존 중 하나 이상의 값이 입력되지 않는다면 caiFlag는 False를 반환

### Example

```java
[
    {
        "resultCode": 200,
        "errorMessage": null,
        "response": "main",
        "document": {
            "grade": "좋음",
            "gradeIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/microdust/microdust.png",
            "pm10Flag": true,
            "pm25Flag": true,
            "pm10": 16,
            "pm25": 14,
            "desc": "야외 활동을 즐겨보세요 !"
        }
    },
    {
        "resultCode": 200,
        "errorMessage": null,
        "response": "other",
        "document": {
            "pm10Flag": true,
            "pm25Flag": true,
            "so2Flag": true,
            "coFlag": true,
            "o3Flag": true,
            "no2Flag": true,
            "pm10": 16,
            "pm25": 14,
            "so2": 10,
            "co": 20,
            "o3": 15,
            "no2": 18
        }
    },
    {
        "resultCode": 200,
        "errorMessage": null,
        "response": "rec",
        "document": {
            "maskIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/mask/dental.png",
            "desc": "미세먼지 좋아요~ 덴탈마스크 추천!",
            "caiFlag": true,
            "cai": 40.193423
        }
    }
]
```

\* resultCode가 200 → 에러 없이 값이 잘 호출 되었음 → errorMessage가 null로 반환되고, document에 각 컴포넌트별 반환값이 저장됨

## 3\) ERROR CODE

| error message | description |
| :---: | :---: |
| API\_PROVISION\_ERROR | API 제공사의 문제 |

* 이 후 에러 메시지와 코드가 추가될 예정입니다.

### Example

```java
{
	[
		{
				"resultCode": 500
				"errorMessage": "API_PROVISION_ERROR"
				"response": "main"
				"document": null
		},
		{
				"resultCode": 200
				"errorMessage": null
				"response": "rec"
				"document": 
				{
						"so2Value": 10,
						"coValue": 20,
						"o3Value": 15,
						"no2Value": 32
				}
		},
		{
				"resultCode": 200
				"errorMessage": null
				"response": "rec"
				"document": 
				{
						"maskIcon": "https://seeme-icon.s3.ap-northeast-2.amazonaws.com/icon/mask/dental.png",
						"desc"‘: "미세먼지 좋아요~ 덴탈마스크 추천!"
						"CAI": 49.32113,
						"CAIFlag": true
				}
		}
	]
}

```

