# Device Edit

### Description

Use **HTTP PUT** to request for a specific device edit

### Syntax

Request URL
```
http://api.mediatek.com/api/v1.0/devices/{device_id}
```

### Parameters

####Header

apiKey:`YOUR_API_KEY_HERE`

####Body

***Data Format: JSON***

The body construct should be in JSON format with the following fields:

| Field Name | Mandatory | Type | Description |
| --- | --- | --- | --- |
| title | Yes | String | Device name |
| desc | Yes | String | Device description |
| tags | No | Array | Device tags |
| location | No | JSON | geoname: string , latitude: float , longitude: float  |

###Example:

***Sample JSON***

```
{
  "title": "test01",
   "desc": "device for testing",
   "tags": ["test01 lab", "temperature"],
   "location": {
                    "latitude" : "24.940225"
                    "longitude" : "121.501913"
                }
}
```

### Method

PUT

## Returns

**Format: JSON**

returns a HTTP response with body text in JSON format, the fields return are:

| Field Name | Type | Description |
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

```
$ Curl -request PUT -data-binary @datafile.txt -header "apiKey: YOUR\_API\_KEY\_HERE" http://v1.0/devices/
```

## See Also

-----------------------------
# Device View

## Description

Use **HTTP GET** to request for a specific device detail

## Syntax

Request URL
```
http://api.mediatek.com/api/v1.0/devices/{device_id}
```

## Parameters

### Header

apiKey:`YOUR_API_KEY_HERE`

## Response

### Header

Content-Type:`application/json`
### Body

**Data Format: JSON**

The response body will construct in JSON format with the following fiedls:

| Field Name | Type |Description|
| --- | --- | --- |
| deviceId | String | Device ID |
| productId | String | Product ID |
| title | String | Title |
| desc | String | Description |
| tags | String Array | tags |
| location | JSON | Device geo-location |
| updateAt | String | Last Device update Timestamp |

**Example: **

Request URL
```
http://api.mediatek.com/api/v1.0/devices/100000009
```
Response Body

```
{
  "results": {
    "deviceId": 100000009,
    "productId": "LI1000000009",
    "title": "Linkit one Weather Station",
    "desc": "With Humidity,Temperature and pressure sensor",
    "tags": [],
    "location": {},
    "updatedAt": "2014-08-29T02:24:16.109Z"
  }
}
```

## See Also

