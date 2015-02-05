# Autosense Overview

Overview of the AutoSense platform goes here




## AutoSense Phone Sensor

**Data Specification**

GPS
Accelerometer



## AutoSense Chest Sensor

**Data Specification**

*sensor_id* - unique identifier for each physical sensor

*channel_id* - one of the following numeric identifiers

| Channel ID | Device |
| ---------- | ------ |
| 0          | Electrocardiogram (ECG) |
| 1          | Accelerometer X axis |
| 2          | Accelerometer Y axis |
| 3          | Accelerometer Z axis |
| 4          | Galvanic Skin Response (GSR)|
| 5          | Respiratory Inductance Plethysmography (RIP) |
| 6          | Battery Level |
| 7          | Skin Temperature |
| 8          | Ambient Temperature |


*data1* - 12-bit integer from the device on *channel_id*

*data2* - 12-bit integer from the device on *channel_id*

*data3* - 12-bit integer from the device on *channel_id*

*data4* - 12-bit integer from the device on *channel_id*

*data5* - 12-bit integer from the device on *channel_id*


## AutoSense Wrist Sensor

**Data Specification**

*sensor_id* - unique identifier for each physical sensor

*channel_id* - one of the following numeric identifiers

| Channel ID | Device |
| ---------- | ------ |
| 20          | Accelerometer X axis |
| 21          | Accelerometer Y axis |
| 22          | Accelerometer Z axis |
| 23          | Gyroscope X axis |
| 24          | Gyroscope Y axis |
| 25          | Gyroscope Z axis |


*data1* - 12-bit integer from the device on *channel_id*

*data2* - 12-bit integer from the device on *channel_id*

*data3* - 12-bit integer from the device on *channel_id*

*data4* - 12-bit integer from the device on *channel_id*

*data5* - 12-bit integer from the device on *channel_id*
