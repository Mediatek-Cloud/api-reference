# DataPoint List

## Description

Use **HTTP GET** request for DataPoint List for a specific sensor of a specific device

### Request URL

```
http://api.mediatek.com/api/v1.0/devices/{device_id}/sensors/{sensor_id}/datapoints.{json/csv}?start={UnixTime}&end={UnixTime}&limit={limit}
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
| sensorId | String | sensor ID |
| content | json | dataPoint Value (vary by sensor type) |


**Example 1: Request for response in json **

Request URL (request for response in json format)
```
http://api.mediatek.com:80/api/v1.0/devices/100000009/sensors/1000000011/datapoints.json
```
Response Body

```
{
  "results": [
    {
      "datapointId": "10000000111409281268924",
      "updatedAt": "1409281268918",
      "sensorId" : "1000000011",
      "content": "{\"value\":\"58.49\"}"
    },
    {
      "datapointId": "10000000111409281271853",
      "updatedAt": "1409281271849",
      "content": "{\"value\":\"58.55\"}"
    }
    ],
  "count": 2
}
```
Please note, the maximum return datapoint is 30

**Example 2: Request for response in csv **

Request URL (request for response in json format)
```
http://api.mediatek.com:80/api/v1.0/devices/100000009/sensors/1000000011/datapoints.csv
```
Response Body

```
10000000111409281268924,1000000011,1409281268918,58.49
10000000111409281271853,1000000011,1409281271849,58.55
```
Please note, the maximum return datapoint is 30

**Example 3: Request for response in given time range **

Request URL (request for response in json format)
```
http://api.mediatek.com:80/api/v1.0/devices/100000009/sensors/1000000011/datapoints.csv?start=1409536800000&end=1409572800000
```
Please note, the unix time is in milliseconds, for human readable time conversion, please refer to http://www.epochconverter.com/

Response Body

```
10000000111409536801906,1000000011,1409536801897,66.12
10000000111409536805466,1000000011,1409536805459,66.15
10000000111409536808863,1000000011,1409536808857,66.18
.....etc
```
Please note, the maximum return datapoint is 30


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
    "url": "http:\\mcs.mediatek.com\api_errorcode?code=1002",
    "description": "You do not have access right to this API"
  }
}
```

