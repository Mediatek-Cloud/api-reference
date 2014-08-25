# MediaTek Cloud Sandbox API

* * *

MediaTek Cloud Sandbox is an external Cloud Services to support LinkIt ONE development IoT devices to:
- Push DataPoints from device to Cloud - eg. geo-location, temperature, humidity, switch-state...etc.
- Pull DataPoints from Cloud to device - eg. simple switching, remote control..etc.

LCloud also provides a web console to allow users to:

- Manage for device and sensor profiles
- Quick view on the DataPoint value over time chart for trends

> LCloud services are fully exposed as External RESTful Services API. LinkIt ONE and other devices capable of making RESTful API call can interact with LCloud.

LCloud services define Device, Sensor and DataPoint Model, all models created under the ownership of a single user (as a representation to a unique ApiKey). The model hierarchy and example is depicted as below:

![](https://documentation.mediatek.com/download/attachments/3409693/image2014-6-24%2010%3A32%3A1.png?version=1&modificationDate=1403577106000&api=v2)

The actions interacting to each model:

| Object| Action|
| --- | --- |
| Device | Create / Delete / Edit / List / View |
| Sensor | Create / Delete / Edit / List / View |
| DataPoint | Create / Delete / Edit / List / History View / Push |

## Prerequisites for Use

1. Users must be a MediaTek Development Network registered user.
2. A registered and logged in user can access LCloud Sandbox Cloud console  to obtain its Apikey for RESTful Services access token.
