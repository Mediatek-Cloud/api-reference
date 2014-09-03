# Sensor Delete

### Description

Use **HTTP DELETE** to request for a specific sensor of a device deletion

### Request URL
```
http://api.mediatek.com/api/v1.0/devices/{device_id}/sensors/{sensor_id}
```

### Action
HTTP DELETE

### Parameters

#### Header

apiKey:`YOUR_API_KEY_HERE`

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
http://api.mediatek.com/api/v1.0/devices/100000012
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
        "url": "http://mcs.mediatek.com/api_errorcode?code=1002",
        "description": "You do not have access right to this API"
    }
}
```

