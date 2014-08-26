# DataPoint Delete

## Description

Use HTTP DELETE to request for a datapoint deletion

## Syntax

URL: http://v1.0/devices//sensors//datapoints/

Qualifier description:

| Qualified | Mandatory | Type | Description |
| --- | --- | --- | --- |
|  | Yes | String | Device Id |
|  | Yes | String | Sensor Id |
|  | Yes | String | key or timestamp |

## Parameters

### Header

apiKey:`YOUR\_API\_KEY\_HERE`

### Method

DELETE

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
$ Curl -request DELETE -header "apiKey: YOUR\_API\_KEY\_HERE" http://v1.0/devices//datapoints/
```

## See Also
