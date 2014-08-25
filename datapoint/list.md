# DataPoint List

## Description

Use HTTP GET to request for a specific datapoint or the last datapoint entry

## Syntax

**For a specific datapoint entry:**

URL: http:///v1.0/devices//sensors//datapoints/

**For the last datapoint entry:**

URL: http:///v1.0/devices//sensors//datapoints

Qualifier description:

|Qualified |Mandatory |Type |Description |
| --- | --- | --- | --- |
|  | Yes | String | Device Id |
|  | Yes | String | Sensor Id |
|  | Yes | String | key or timestamp |

## Parameters

### Header

apiKey:YOUR\_API\_KEY\_HERE

## Method

GET

## Returns

**Format: JSON**

returns a HTTP response with body text in JSON format, the fields return are:

**Value Type Sensor**

|Field Name|Type |Description|
| --- | --- | --- |
| RC | Integer | Return Codefour digit representation1000 : Normal1xxx : Warning2xxx : Error |
| value | float | value |

**Example:**

**Sample JSON**

```
{ "RC" : 1000,"value":294.34}
```

**GPS Type Sensor**

|Field Name |Type |Description |
| --- | --- | --- |
| RC | Integer | Return Codefour digit representation1000 : Normal1xxx : Warning2xxx : Error |
| value | JSON | Lat: float Latitude Lng: float Longtitude Spd: float Speed Offs: float offset |

**Example:**

**Sample JSON**

```
{ "RC" : 1000,"value":294.34:{"lat":35.4567,"lng":46.1234,"spd":98.2}}
```

**Generic Type Sensor**

|Field Name |Type |Description |
| --- | --- | --- |
| RC | Integer | Return Code |
| value | self-define | value |

**Example:**

**Sample JSON**

```
{ "RC" : 1000,"value":"datalog 01"}
```



## Authentication

Need to add API key in HTTP Header for authentication

## Example (use of curl):

Curl ¡Vrequest GET ¡Vheader "apiKey: YOUR\_API\_KEY\_HERE" http:///v1.0/devices///datapoints/

## See Also
