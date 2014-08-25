# Device Delete

## Description

Use HTTP DELETE to request for a device deletion

## Syntax

URL: http:///v1.0/devices/

Qualifier description:

| Qualified| Mandatory | Type | Description |
| --- | --- | --- | --- |
|  | Yes | String | Device\_id |

## Parameters

### Header

apiKey:YOUR\_API\_KEY\_HERE

### Method

DELETE

## Returns

**Format: JSON**

returns a HTTP response with body text in JSON format, the fields return are:

|Field Name|Type |Description |
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

Curl ¡Vrequest DELETE ¡Vheader "apiKey: YOUR\_API\_KEY\_HERE" http:///v1.0/devices/

## See Also



