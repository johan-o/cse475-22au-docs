---
layout: post
title:  Week 8 Notebook
date:   2022-11-15 13:00:00 -0700
---
## Tuesday, 15 November 2022
* Finally got BLE functionality: setting the RTC based on data transmitted over bluetooth

![RTC Setting](/cse475-22au-docs/assets/week8-notebook/ble-rtc.png)

There are two BLE characteristics and services, one each for setting the RTC and for the sensor data
transmitted from the ESP32. 

### RTC
```
#define RTC_SERVICE_UUID          "e0894506-fda6-43d4-b1a4-6813e608b549"
#define RTC_CHARACTERISTIC_UUID   "28348d85-8d9a-4733-bcb5-f45ea46851b4"
```
Use these UUIDs for the RTC. Write a 32-bit value into the characteristic, and the ESP32's real time clock 
will update to the new value. 

The ESP will wait until a device is paired with it and the RTC is set before starting to read any data.

### Data
The data is stored internally on the ESP32 with a struct:

```
struct TimeStampedData {
  uint32_t time;
  uint16_t pm10;
  uint16_t pm25;
  uint16_t pm100;
};
```

This data is placed in the data characteristic:
```
#define DATA_SERVICE_UUID         "4fafc201-1fb5-459e-8fcc-c5c9c331914b"
#define DATA_CHARACTERISTIC_UUID  "beb5483e-36e1-4688-b7f5-ea07361b26a8"
```
This characteristic is _notified_ upon a change. May want to change this to an indication so the phone
has to receive data.

Byte layout of the data:

| Bytes | Stored Data | Data Type |
| --- | --- | --- | 
| 0:3 | Time | Signed 32-bit int |
| 4:5 | PM1.0 | Unsigned 16-bit int |
| 6:7 | PM2.5 | Unsigned 16-bit int |
| 8:9 | PM10.0 | Unsigned 16-bit int |
