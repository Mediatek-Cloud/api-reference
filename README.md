# MediaTek Cloud Sandbox API

* * *

MediaTek Cloud Sandbox is an external Cloud Services to support LinkIt ONE development IoT devices to:
- Push DataPoints from device to Cloud - eg. geo-location, temperature, humidity, switch-state...etc.
- Pull DataPoints from Cloud to device - eg. simple switching, remote control..etc.

LCloud also provides a web console to allow users to:

- Manage for device and sensor profiles
- Quick view on the DataPoint value over time chart for trends

> LCloud services are fully exposed as External RESTful Services API. LinkIt ONE and other devices capable of making RESTful API call can interact with LCloud.

LCloud services define Product, Device, Sensor and DataPoint Model, all models created under the ownership of a single user (as a representation to a unique ApiKey). Take a weather staion device as an example, the model hierarchy can be designed as below:

<img src="https://raw.githubusercontent.com/Mediatek-Cloud/api-reference/master/graphics/data-hirachy.JPG" width="325px"/>


The sequence of creating a weather station device is to:

1. Define a **PRODUCT** namely "Weather Station Model 01".
2. Once the PROUDCT is created, we can create **DEVICE** within this specific PRODUCT, the relationship between PRODUCT and DEVICE is one to many.
3. Once a DEVICE is created, we can create **SENSOR** within this specific DEVICE, the relationship between DEVICE and SENSOR is one to many.
4. For this specific example, we create four SENSORS with this device, SENSOR is the placeholder for **DATAPOINTS** which represents the actual data we wish to store or retrieve.

The actions interacting to each model:

| Object| Action| API| Management Console
| --- | --- |
| PRODUCT| Create / Delete / Edit / List / View | x | v |
| DEVICE | Create / Delete / Edit / List / View | v | v |
| SENSOR | Create / Delete / Edit / List / View | v | v |
| DATAPOINT | Create / Delete / Edit / List / History View / Push | v | v |

## Prerequisites for Use

1. Users must be a MediaTek Development Network registered user.
2. A registered and logged in user can access LCloud Sandbox Cloud console  to obtain its Apikey for RESTful Services access token.
