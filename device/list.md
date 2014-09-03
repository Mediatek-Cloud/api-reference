# Device View

### Description

Use **HTTP GET** to request for detail of a specific device

### Request URL

```
http://api.mediatek.com/api/v1.0/devices/{device_id}
```

### Action
HTTP GET

### Parameters

#### Header

apiKey:`YOUR_API_KEY_HERE`

### Response

#### Response Code
200

#### Response Header

Content-Type:`application/json`
#### Response Body

***Data Format: JSON***

The response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| deviceId | String | Device ID |
| productId | String | Product ID |
| title | String | Title |
| desc | String | Description |
| tags | String Array | tags |
| location | JSON | Device geo-location |
| updateAt | String | Last Device update Timestamp |

**Example: **

Request URL
```
http://api.mediatek.com/api/v1.0/devices/100000009
```
Response Body

```
{
  "results": {
    "deviceId": 100000009,
    "productId": "LI1000000009",
    "title": "Linkit one Weather Station",
    "desc": "With Humidity,Temperature and pressure sensor",
    "tags": [],
    "location": {},
    "updatedAt": "2014-08-29T02:24:16.109Z"
  }
}
```

### Error Response

When error is incurred, the response code will be non-200 and the response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| code | Integer | Error Code |
| url | String | url to API Error detail page |
| description | String | Error Description |

**Example: **
```
{
    "results": {
        "code": 1002,
        "url": "http://mcs.mediatek.com/api_errorcode?code=1002",
        "description": "You do not have access right to this API"
    }
}
```

