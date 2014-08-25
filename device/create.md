# Device Create

## Description

Use HTTP POST to request for a device creation

## Syntax

URL: http://v1.0/devices

## Parameters

### Header

apiKey:`YOUR\_API\_KEY\_HERE`

### Body

**Data Format: JSON**

The body construct should be in JSON format with the following fields:

| Field Name | Mandatory | Type |Description|
| --- | --- | --- | --- |
| title | Yes | String | Device name |
| desc | No | String | Device description |
| tags | No | Array | Device tags |
| location | No | JSON | geoname:string /v1.0/devices

## See Also



