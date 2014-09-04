# DataPoint Create

### Description

Use **HTTP POST** to request for datapoint creation on a specific sensor of a specific device

### Request URL

```
http://api.mediatek.com/api/v1.0/devices/{device_id}/sensors/{sensor_id}
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
        "url": "http://mcs.mediatek.com/api_errorcode?code=1002",
        "description": "You do not have access right to this API"
    }
}
```



-------------------------------------------------------


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
        "url": "http://mcs.mediatek.com/api_errorcode?code=1002",
        "description": "You do not have access right to this API"
    }
}
```




---------------------------------------------------------


# DataPoint Create

## Description

Use HTTP POST to request for a datapoint creation for a sensor

## Syntax

URL: http://v1.0/devices//sensors//datapoints

Qualifier description:

| Qualified | Mandatory | Type| Description|
| --- | --- | --- | --- |
|  | Yes | String | Device Id |
|  | Yes | String | Sensor Id |

## Parameters

### Header

apiKey:`YOUR\_API\_KEY\_HERE`

### Body

**Data Format: JSON**

There are three types of sensor: **Value** , **GPS** and **Generic** type:

**Value Type Sensor**

The body construct should be in JSON format with the following fields:

| Field Name | Mandatory | Type | Description|
| --- | --- | --- | --- |
| timestamp | Yes | timestamp | Key (timestamp is expressed according to ISO 8601 format
2014-06-10T13:52:43+00:00 |
| value | Yes | float | value |

#### Example:

**Sample JSON**

```
{"timestamp":"2014-03-15T16:13:14+08:00","value":294.34}
```

**GPS Type Sensor**

The body construct should be in JSON format with the following fields:

| Field Name | Mandatory | Type | Description |
| --- | --- | --- | --- |
| timestamp | Yes | timestamp | Key (timestamp is expressed according to ISO 8601 format
2014-06-10T13:52:43+00:00 |
| value | Yes | JSON | Lat: float Latitude Lng: float Longtitude Spd: float Speed Offs: float offset |

#### Example:

**Sample JSON**

```
{"timestamp":"2014-03-15T16:13:14+08:00","value":{"lat":35.4567,"lng":46.1234,"spd":98.2}}{"timestamp":"2014-03-15T16:13:14+08:00","value":{"lat":35.4567,"lng":46.1234,"spd":98.2,"offs":"yes"}}
```

**Generic Type Sensor**

The body construct should be in JSON format with the following fields:

| Field Name | Mandatory | Type | Description |
| --- | --- | --- | --- |
| key | Yes | String | Key, maximum 128 char |
| value | Yes | Self-define | Self-define, maximum 1024 char |

#### Example:

**Sample JSON**

```
{"key":"ABCDEFG01","value":"data log 01"}
```

Please note: One or more DataPoints can be created in one single HTTP POST

## Method

POST

## Returns

**Format: JSON**

returns a HTTP response with body text in JSON format, the fields return are:

| Field Name | Type | Description |
| --- | --- | --- |
| RC | Integer | Return Codefour digit representation1000 : Normal1xxx : Warning2xxx : Error |

**Example:**

**Sample JSON**

```
{ "RC" : 1000}
```

## Authentication

Need to add API key in HTTP Header for authentication

## Example (use of curl):

```
$ Curl -request PUT -data-binary @datafile.txt -header "apiKey: YOUR\_API\_KEY\_HERE" http://v1.0/devices//datapoints
```


## See Also

