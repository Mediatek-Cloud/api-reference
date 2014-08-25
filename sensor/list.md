# Sensor List

## Description

Use HTTP GET to request for a sensor list

## Syntax

URL: http://v1.0/devices//sensors

Qualifier description:

| Qualified|Mandatory| Type| Description|
| --- | --- | --- | --- |
|  | Yes | String | Device Id |

## Parameters

### Header

apiKey:`YOUR\_API\_KEY\_HERE`

## Method

GET

## Returns

**Format: JSON**

returns a HTTP response with body text in JSON format, the fields return are:

|Field Name|Type |Description |
| --- | --- | --- |
| RC | Integer | Return Codefour digit representation1000 : Normal1xxx : Warning2xxx : Error |
| sensor\_id | String | Sensor Id |
| type | String | Sensor Type |
| title | String | Sensor Name |
| desc | String | Sensor Description |

## Example

**Sample JSON**

```
{ "RC": 1000,{ "sensor_id": "12345", "type":"value", "title": "test01", "about": "sensor for testing"},{ "sensor_id": "12346", "type":"gps", "title": "test02", "about": "sensor for testing"}}
```

## Authentication

Need to add API key in HTTP Header for authentication

## Example (use of curl):

```
$ Curl -request GET -header "apiKey: YOUR\_API\_KEY\_HERE" http://v1.0/devices//sensors
```

## See Also
