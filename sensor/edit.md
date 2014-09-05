# Sensor Edit

## Description

Use **HTTP PUT** to request for a specific sensor edit of a specific device


### Request URL

```
http://api.mediatek.com/api/v1.0/devices/{device_id}/sensors/{sensor_id}
```

### Action
HTTP PUT

### Parameters

#### Header

apiKey:`YOUR_API_KEY_HERE`

#### Body

***Data Format: JSON***

|Field Name|Mandatory|Type|Description|
| --- | --- | --- | --- |
| title | No | String | Sensor name |
| desc | No | String | Sensor description |
| tags | No | Array | Sensor tags |
| unit | No | String | unit of the value |

Please note: Sensor type cannot be changed once created

###Example:

***Sample JSON***

```
{
  "title": "Temperature Sensor 01",
  "desc": "Temperature Sensor description"
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

| Field Name | Type | Description |
| --- | --- | --- |
| results | Strings | resturns "success" only|

**Example:**

Request URL
```
http://api.mediatek.com/api/v1.0/devices/100000012/sensors/1000000027
```

Response Body

```
{
    "results": "success"
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

