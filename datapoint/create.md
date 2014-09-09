# DataPoint Create

### Description

Use **HTTP POST** to request for datapoint creation on a specific sensor of a specific device

### Request URL

```
http://api.mediatek.com/api/v1.0/devices/{device_id}/sensors/{sensor_id}/datapoints
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
| content | Yes | json |  | |


#### Example:

Request URL
```
http://api.mediatek.com:80/api/v1.0/devices/100000012/sensors/1000000025/datapoints
```

Request Body

For Time-Value datapoint example:
```
{
  "type" : "Time-Value",
  "time": "1409714629628",
  "content": {

    "value": 20.3
  }
}
```

For GPS datapoint example:
```
{
  "type" : "GPS",
  "time": "1409714629628",
  "content": {
    "latitude": 25.015228750967108,
    "longtitude": 121.50960445404053

  }
}
```
For Switch datapoint example:
```
{
  "type": "Switch",
  "time": "1409714629628",
  "content": {
    "status": "on"
  }
}
```
Please note, for "Time-Value", "GPS" and "Switch" datapoint, "time" is in unix-time format the milliseconds and is optional. If not provided, system will generate timestamp at the time of receiving this API call.


For Key-Value datapoint example:

```
{
  "type": "Key-Value",
  "content": {
    "key": "car_model",
    "value": "Ford"
  }
}
```

### Response

#### Response Code
200

#### Response Header

Content-Type:`application/json`
#### Response Body

####Example:

```
{
  "results": "success",
  "datapointId": "10000000251409881841905"
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

