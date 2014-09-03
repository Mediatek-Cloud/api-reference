# Device View

### Description

Use **HTTP GET** to request for a specific device detail

### Request URL

```
http://api.mediatek.com/api/v1.0/devices/{device_id}
```

### Parameters

#### Header

apiKey:`YOUR_API_KEY_HERE`

### Response

#### Header

Content-Type:`application/json`
#### Body

***Data Format: JSON***

The response body will construct in JSON format with the following fiedls:

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

### See Also
