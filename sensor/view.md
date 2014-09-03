# Sensor View

## Description

Use **HTTP GET** for detail of a specific sensor of a specific device

### Request URL

```
http://api.mediatek.com/api/v1.0/devices/{device_id}/sensors/{sensor_id}
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
| sensorId | String | Sensor ID |
| type | {Time-Value, Switch, GPS, Key-Value} | switch type |
| title | String | Title |
| desc | String | Description |
| unit | String Array | For Time-Value sensors only|
| updateAt | String | Last Device update Timestamp |

**Example: **

Request URL
```
http://api.mediatek.com:80/api/v1.0/devices/100000009/sensors/1000000011
```
Response Body

```
{
  "results": [
    {
      "sensorId": 1000000011,
      "type": "Time-Value",
      "title": "Humidity",
      "desc": null,
      "unit": "%",
      "updatedAt": "2014-08-29T02:26:30.829Z"
    }
  ]
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
# View
