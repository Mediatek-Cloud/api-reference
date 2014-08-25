# Device List

## Description

Use HTTP GET to request for a device list

## Syntax

URL: http:///v1.0/devices

## Parameters

### Header

apiKey:YOUR\_API\_KEY\_HERE

### Method

GET

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
| device\_id | String | Device ID |
| title | String | Device name |
| desc | String | Device description |
| location | JSON | geoname: string , latitude: float , longitude: float  |

**Example:**

**Sample JSON**

```
{ "RC" : 1000, { "device_id": "1234567890", "title": "test01", "desc": "device for testing", "location": { "geoname" : "Office1", "latitude" : "24.940225", "longitude" : "141.533913"}},{ "device_id": "1234567891" "title": "test02", "desc": "device for testing", "location": { "geoname" : "Office2", "latitude" : "28.943203", "longitude" : "131.501913"}}}
```

## Authentication

Need to add API key in HTTP Header for authentication

## Example (use of curl):

Curl ¡Vrequest GET ¡Vheader "apiKey: YOUR\_API\_KEY\_HERE" http:///v1.0/devices

## See Also
