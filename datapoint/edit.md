# DataPoint Edit

## Description

Use **HTTP PUT** to request for a specific dataPoint edit of a sensor of a specific device


### Request URL

```
http://api.mediatek.com/api/v1.0/devices/{device_id}/sensors/{sensor_id}/datapoints/{datapoint_id}
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


-----------------------------------------------------

# DataPoint Edit

## Description

Use HTTP PUT to request for a datapoint edit

## Syntax

URL: http://v1.0/devices//sensors//datapoints/

Qualifier description:

| Qualified | Mandatory | Type | Description |
| --- | --- | --- | --- |
|  | Yes | String | Device Id |
|  | Yes | String | Sensor Id |
|  | Yes | String | key or timestamp |

## Parameters

### Header

apiKey:`YOUR\_API\_KEY\_HERE`

### Body

**Data Format: JSON**

There are three types of sensor: **Value** , **GPS** and **Generic** type:

**Value Type Sensor**

The body construct should be in JSON format with the following fields:

| Field Name | Mandatory | Type | Description |
| --- | --- | --- | --- |
| value | Yes | float | value |

#### Example:

**Sample JSON**

```
{"value":294.34}
```

**GPS Type Sensor**

The body construct should be in JSON format with the following fields:

| Field Name | Mandatory | Type | Description |
| --- | --- | --- | --- |
| value | Yes | JSON | Lat: float Latitude Lng: float Longtitude Spd: float Speed Offs: float offset |

#### Example:

**Sample JSON**

```
{"value":{"lat":35.4567,"lng":46.1234,"spd":98.2,"offs":"yes"}}
```

**Generic Type Sensor**

The body construct should be in JSON format with the following fields:

| Field Name | Mandatory | Type | Description |
| --- | --- | --- | --- |
| value | Yes | Self-define | Self-define, maximum 1024 char |

#### Example:

**Sample JSON**

```
{"value":"data log 01"}
```

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
$ Curl -request PUT -data-binary @datafile.txt -header "apiKey: YOUR\_API\_KEY\_HERE" http://v1.0/devices//datapoints/
```

## See Also
