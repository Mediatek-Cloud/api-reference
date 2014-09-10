# DataPoint Edit

## Description

Use **HTTP PUT** to request for a specific DataPoint Edit of a specific sensor edit of a specific device


### Request URL

```
http://api.mediatek.com/api/v1.0/devices/{device_id}/sensors/{sensor_id}/datapoints/{datapoint_id}
```

### Action
HTTP PUT

### Parameters

#### Header

apiKey:`YOUR_API_KEY_HERE`
Content-Type:application/json

#### Body

***Data Format: JSON***

|Field Name|Mandatory|Type|Description|
| --- | --- | --- | --- ||
| time | No | String | timestamp |
| content | Yes | json |  | |

Please note: Sensor type cannot be changed once created

###Example:

***Sample JSON***

```
{
  "content": {
     "value": 22.3
  }
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
http://api.mediatek.com/api/v1.0/devices/100000012/sensors/1000000026/datapoints/10000000261410231119907
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
