# DataPoint MultiCreate

### Description

Use **HTTP POST** to request for multiple datapoint creation on one or more sensor(s) of a specific device

### Request URL

```
http://api.mediatek.com/api/v1.0/devices/{device_id}/datapoints.{json/csv}
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
| sensorId | Yes | String | Sensor Id |
| content | Yes | json |  | |


#### Example:

Request URL (JSON)
```
http://api.mediatek.com:80/api/v1.0/devices/100000012/datapoints.json
```

Request Body (JSON)

For placing 4 sensor datapoint in one API example:
```
[
  {
    "sensorId": "1000000026",
    "content": {
      "time": 1409714629628,
      "value": 20.3
    }
  },
  {
    "sensorId": "1000000023",
    "content": {
      "time": 1409714629628,
      "status": "on"
    }
  },
  {
    "sensorId": "1000000024",
    "content": {
      "time": 1409714629628,
      "latitude": 25.015228750967,
      "longtitude": 121.50960445404
    }
  },
  {
    "sensorId": "1000000025",
    "content": {
      "key": "car_model",
      "value": "Ford"
    }
  }
]
```

Please note, for "Time-Value", "GPS" and "Switch" datapoint, "time" is in unix-time format the milliseconds and is optional. If not provided, system will timestamp it at the time of receiving this datapoint creation request.

Request URL (CSV)
```
http://api.mediatek.com:80/api/v1.0/devices/100000012/datapoints.csv
```

For placing 4 sensor datapoint in one API example:

Request Body (CSV)

For placing 4 sensor datapoint in one API example:
```
1000000026,1409714629628,20.3
1000000023,1409714629628,on
1000000024,1409714629628,25.015228750967,121.50960445404
1000000025,1409714629628,car_model,Ford

```
Please note, for "Time-Value", "GPS" and "Switch" datapoint, "time" is in unix-time format the milliseconds and is optional. If not provided, system will timestamp it at the time of receiving this datapoint creation request.

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

####Example:

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
        "url": "http://mcs.mediatek.com/api_errorcode?code=1002",
        "description": "You do not have access right to this API"
    }
}
```


