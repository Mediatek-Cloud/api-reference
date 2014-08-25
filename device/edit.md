# Device Edit

## Description

Use HTTP PUT to request for a device edit

## Syntax

URL: http:///v1.0/devices/

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
| title | Yes | String | Device name |
| desc | No | String | Device description |
| tags | No | Array | Device tags |
| location | No | JSON | geoname: string , latitude: float , longitude: float  |

#### Example:

**Sample JSON**

```
{ "title": "test01", "desc": "device for testing", "tags": ["test01 lab", "temperature"], "location": { "geoname" : "office", "latitude" : "24.940225" "longitude" : "121.501913"}}
```

### Method

PUT

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

**Example:**

**Sample JSON**

```
{ "RC" : 1000 }
```

## Authentication

Need to add API key in HTTP Header for authentication

## Example (use of curl):

Curl ¡Vrequest PUT ¡Vdata-binary @datafile.txt ¡Vheader "apiKey: YOUR\_API\_KEY\_HERE" http:///v1.0/devices/

## See Also
