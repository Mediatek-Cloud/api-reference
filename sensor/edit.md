# Sensor Edit

## Description

Use HTTP PUT to request for a sensor edit

## Syntax

URL: http:///v1.0/devices//sensors/

Qualifier description:

| Qualified | Mandatory | Type | Description |
| --- | --- | --- | --- |
|  | Yes | String | Device Id |
|  | Yes | String | Sensor Id |

## Parameters

### Header

apiKey:YOUR\_API\_KEY\_HERE

### Body

**Data Format: JSON**

There are three types of sensor: **Value** , **GPS** and **Generic** type:

**Value Type Sensor**

The body construct should be in JSON format with the following fields:

|

Field Name

 |

Mandatory

 |

Type

 |

Description

 |
| --- | --- | --- | --- |
| title | Yes | String | Sensor name |
| desc | No | String | Sensor description |
| tags | No | Array | Sensor tags |
| unit | No | JSON | name: string, symbol: string |

#### Example:

**Sample JSON**

```
{ "title": "test01", "desc": "sensor for testing", "tags": ["sensor tag1", "sensor tag2"], "unit": { "name" : "temperature", "symbol" : "C"}}
```

**GPS and Generic Type Sensor**

The body construct should be in JSON format with the following fields:

| Field Name | Mandatory | Type | Description |
| --- | --- | --- | --- |
| title | Yes | String | Sensor name |
| desc | No | String | Sensor description |
| tags | No | Array | Sensor tags |

#### Example:

**Sample JSON**

```
{ "title": "test01", "desc": "sensor for testing", "tags": ["sensor tag1", "sensor tag2"],}
```

Please note: Sensor type cannot be changed once created

## Method

PUT

## Returns

**Format: JSON**

returns a HTTP response with body text in JSON format, the fields return are:

| Field Name |Type | Description |
| --- | --- | --- |
| RC | Integer | Return Code |

**Example:**

**Sample JSON**

```
{ "RC" : 1000}
```

## Authentication

Need to add API key in HTTP Header for authentication

## Example (use of curl):

Curl ¡Vrequest PUT ¡Vdata-binary @datafile.txt ¡Vheader "apiKey: YOUR\_API\_KEY\_HERE" http:///v1.0/devices//

## See Also
