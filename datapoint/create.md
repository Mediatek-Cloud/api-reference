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

