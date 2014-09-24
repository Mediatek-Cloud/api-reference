# Get Last DataPoint (Device Level)

## Description

Use **HTTP GET** request to obtain the last DataPoint for a specific sensor of a specific device

### Request URL

```
http://api.mediatek.com/api/v1.0/devices/{device_id}/datapoints/last.{json/csv}
```

### Action
HTTP GET

### Parameters

#### Header

apiKey:`YOUR_API_KEY_HERE`
Content-Type:application/json

### Response

#### Response Code
200

#### Response Header

Content-Type:`application/json`
#### Response Body

***Data Format: JSON***

The response body will construct in JSON format with the following fields:

| Field Name | Type |Description|
| --- | --- | --- |
| dataPointId | String | dataPoint ID |
| updatedAt | String | Last Device update Timestamp |
| content | json | dataPoint Value (vary by sensor type) |


**Example 1: Request for response in json **

Request URL (request for response in json format)
```
http://api.mediatek.com:80/api/v1.0/devices/100000009/datapoints/last.json
```
Response Body

```
{
  "results": [
    {
      "datapointId": "10000000111409730143369",
      "updatedAt": "1409730143364",
      "sensorId" : "1000000011",
      "content": "{\"value\":\"69.03\"}"
    }
  ]
}
```

**Example 2: Request for response in csv **

Request URL (request for response in json format)
```
http://api.mediatek.com:80/api/v1.0/devices/100000009/datapoints/last.csv
```
Response Body

```
10000000111409281268924,1000000011,1409281268918,58.49
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
# Last (Device Level)
