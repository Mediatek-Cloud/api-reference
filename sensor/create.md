# Sensor Create

## Description

Use HTTP POST to request for a sensor creation

## Syntax

URL: http:///v1.0/devices//sensors

Qualifier description:

|

Qualified

 |

Mandatory

 |

Type

 |

Description

 |
| --- | --- | --- | --- |
|  | Yes | String | Device\_id |

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
| type | Yes | String | Sensor Type, set as "value" |
| title | Yes | String | Sensor name |
| desc | No | String | Sensor description |
| tags | No | Array | Sensor tags |
| unit | No | JSON | name: string, symbol: string |

#### Example:

**Sample JSON**

```
{ "type":"value", "title": "test01", "desc": "sensor for testing", "tags": ["sensor tag1", "sensor tag2"], "unit": { "name" : "temperature", "symbol" : "C"}}
```

**GPSType Sensor**

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
| type | Yes | String | Sensor Type, set as "gps" |
| title | Yes | String | Sensor name |
| desc | No | String | Sensor description |
| tags | No | Array | Sensor tags |

#### Example:

**Sample JSON**

```
{ "type":"gps", "title": "test01", "desc": "sensor for testing", "tags": ["sensor tag1", "sensor tag2"],}
```

**Generic** Type Sensor

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
| type | Yes | String | Sensor Type, set as "gen" |
| title | Yes | String | Sensor name |
| desc | No | String | Sensor description |
| tags | No | Array | Sensor tags |

#### Example:

**Sample JSON**

```
{ "type":"gen", "title": "test01", "desc": "sensor for testing", "tags": ["sensor tag1", "sensor tag2"],}
```

Please note: One or more sensors can be created under one single HTTP post under one specific device

## Method

POST

## Returns

**Format: JSON**

returns a HTTP response with body text in JSON format, the fields return are:

|

Field Name

 |

Type

 |

Description

 |
| --- | --- | --- |
| RC | Integer | Return Codefour digit representation1000 : Normal1xxx : Warning2xxx : Error |
| sensor\_id | String | Sensor ID |

**Example:**

**Sample JSON**

```
{ "RC" : 1000, "sensor_id": "12345"}
```

## Authentication

Need to add API key in HTTP Header for authentication

## Example (use of curl):

Curl ¡Vrequest POST ¡Vdata-binary @datafile.txt ¡Vheader "apiKey: YOUR\_API\_KEY\_HERE" http:///v1.0/devices/

## See Also


