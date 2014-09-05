# Sensor Create

### Description

Use **HTTP POST** to request for a sensor creation on a specific device

### Request URL

```
http://api.mediatek.com/api/v1.0/devices/{device_id}/sensors
```

### Action
HTTP POST

### Parameters

#### Header

apiKey:`YOUR_API_KEY_HERE`

#### Body

***Data Format: JSON***

There are four types of sensors can be defined: Time-Value, Switch, GPS, Key-Value

The body construct should be in JSON format with the following fields:

|Field Name|Mandatory|Type|Description|
| --- | --- | --- | --- |
| type | Yes | String | Sensor Type, set to one of the following:  "Time-Value", "Switch", "Key-Value", "GPS" |
| title | Yes | String | Sensor name |
| desc | No | String | Sensor description |
| tags | No | Array | Sensor tags |
| unit | No | String | unit of the value |

#### Example:

Request URL
```
http://api.mediatek.com:80/api/v1.0/devices/100000012/sensors
```

Request Body

```
{
  "type": "Time-Value",
  "title": "Temperature Sensor example",
  "desc": "Temperature Sensor description",
  "unit": "Degree"
}
```

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
| results | Strings | resturns "success" only|
| sensorId | String | created Sensor ID |

####Example:

```
{
  "results": "success",
  "sensorId": 1000000027
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
    "url": "http:\\mcs.mediatek.com\api_errorcode?code=1002",
    "description": "You do not have access right to this API"
  }
}
```


