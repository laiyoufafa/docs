# Sensor Overview


Sensors in OpenHarmony are an abstraction of underlying sensor hardware. Your application can access the underlying sensor hardware via the sensors. Using the APIs provided by sensors, you can query sensors on your device, subscribe to sensor data, customize algorithms based on sensor data, and develop various sensor-based applications, such as compass, motion-controlled games, and fitness and health applications.


A sensor is a device to detect events or changes in an environment and send messages about the events or changes to another device (for example, a CPU). Generally, a sensor is composed of sensitive components and conversion components. Sensors are the cornerstone of the IoT. A unified sensor management framework is required to achieve data sensing at a low latency and low power consumption, thereby keeping up with requirements of "1+8+N" products or business in the Seamless AI Life Strategy. The sensor list is as follows:

| Type                             | Name              | Description                                                        | Usage                                |
| --------------------------------------- | ------------------ | ------------------------------------------------------------ | ---------------------------------------- |
| SENSOR_TYPE_ACCELEROMETER               | Acceleration sensor      | Measures the acceleration (including the gravity acceleration) applied to a device on three physical axes (X, Y, and Z), in the unit of m/s<sup>2</sup>.| Detecting the motion status                            |
| SENSOR_TYPE_ACCELEROMETER_UNCALIBRATED  | Uncalibrated acceleration sensor| Measures the uncalibrated acceleration (including the gravity acceleration) applied to a device on three physical axes (X, Y, and Z), in the unit of m/s<sup>2</sup>.| Measuring the acceleration bias estimation                      |
| SENSOR_TYPE_LINEAR_ACCELERATION         | Linear acceleration sensor  | Measures the linear acceleration (excluding the gravity acceleration) applied to a device on three physical axes (X, Y, and Z), in the unit of m/s<sup>2</sup>.| Detecting the linear acceleration in each axis          |
| SENSOR_TYPE_GRAVITY                     | Gravity sensor        | Measures the gravity acceleration applied to a device on three physical axes (X, Y, and Z), in the unit of m/s<sup>2</sup>.| Measuring the gravity                            |
| SENSOR_TYPE_GYROSCOPE                   | Gyroscope sensor      | Measures the rotation angular velocity of a device on three physical axes (X, Y, and Z), in the unit of rad/s.| Measuring the rotation angular velocity                        |
| SENSOR_TYPE_GYROSCOPE_UNCALIBRATED      | Uncalibrated gyroscope sensor| Measures the uncalibrated rotation angular velocity of a device on three physical axes (X, Y, and Z), in the unit of rad/s.| Measuring the bias estimation of the rotation angular velocity              |
| SENSOR_TYPE_SIGNIFICANT_MOTION          | Significant motion sensor  | Checks whether a device has a significant motion on three physical axes (X, Y, and Z). The value **0** means that the device does not have a significant motion, and **1** means the opposite.| Detecting significant motions of a device          |
| SENSOR_TYPE_PEDOMETER_DETECTION         | Pedometer detection sensor  | Detects whether a user takes a step. The value can be **0** (the user does not take a step) or **1** (the user takes a step).| Detecting whether a user takes a step            |
| SENSOR_TYPE_PEDOMETER                   | Pedometer sensor      | Records the number of steps a user has walked.                                          | Providing the number of steps a user has walked              |
| SENSOR_TYPE_AMBIENT_TEMPERATURE         | Ambient temperature sensor    | Measures the ambient temperature, in the unit of degree Celsius (°C).             | Measuring the ambient temperature                            |
| SENSOR_TYPE_MAGNETIC_FIELD              | Magnetic field sensor        | Measures the magnetic field on three physical axes (X, Y, and Z), in the unit of μT.| Creating a compass                              |
| SENSOR_TYPE_MAGNETIC_FIELD_UNCALIBRATED | Uncalibrated magnetic field sensor  | Measures the uncalibrated magnetic field on three physical axes (X, Y, and Z), in the unit of μT.| Measuring the magnetic field bias estimation                        |
| SENSOR_TYPE_HUMIDITY                    | Humidity sensor        | Measures the ambient relative humidity, in a percentage (%).             | Monitoring the dew point, absolute humidity, and relative humidity            |
| SENSOR_TYPE_BAROMETER                   | Barometer sensor      | Measures the barometric pressure, in the unit of hPa or mbar.        | Measuring the barometric pressure                            |
| SENSOR_TYPE_ORIENTATION                 | Orientation sensor        | Measures the rotation angles of a device on three physical axes (X, Y, and Z), in the unit of rad.| Providing the three orientation angles of the screen             |
| SENSOR_TYPE_ROTATION_VECTOR             | Rotation vector sensor    | Measures the rotation vector of a device. It is a composite sensor that generates data from the acceleration sensor, magnetic field sensor, and gyroscope sensor.| Detecting the orientation of a device in the East, North, Up (ENU) Cartesian coordinate system        |
| SENSOR_TYPE_PROXIMITY                   | Proximity sensor      | Measures the distance between a visible object and the device screen.                | Measuring the distance between a person and the device during a call                  |
| SENSOR_TYPE_AMBIENT_LIGHT               | Ambient light sensor      | Measures the ambient light intensity of a device, in the unit of lux.                             | Automatically adjusting the screen brightness and checking whether the screen is covered on the top|
| SENSOR_TYPE_HEART_RATE                  | Heart rate sensor        | Measures the heart rate of a user.                                          | Providing users' heart rate data              |
| SENSOR_TYPE_WEAR_DETECTION              | Wear detection sensor    | Checks whether a user is wearing a wearable device.                                            | Detecting wearables            |
| SENSOR_TYPE_HALL                        | Hall effect sensor        | Detects a magnetic field around a device.                                | Smart cover mode of the device                          |


## Working Principles

The following modules work cooperatively to implement OpenHarmony sensors: Sensor API, Sensor Framework, Sensor Service, and HDF layer.

  **Figure 1** How the sensor works

![fad1a124-a90e-460f-84fc-e87d6caebb21](figures/fad1a124-a90e-460f-84fc-e87d6caebb21.png)

- Sensor API: provides APIs for performing basic operations on sensors, including querying the sensor list, subscribing to or unsubscribing from sensor data, and executing control commands. This module makes application development simpler.

- Sensor Framework: manages sensor data subscription, creates and destroys data channels, subscribes to or unsubscribes from sensor data, and implements communication with the Sensor Service module.

- Sensor Service: interacts with the HD_IDL module to receive, parse, and distribute data, manages foreground and background policies and sensors of a device, and controls sensor permissions.

- HDF layer: selects proper policies based on the hardware first in first out (FIFO) and frequency, and adapts to different devices.


## Constraints

1. To obtain data of the following sensors, you must claim the required permissions.

    Table 7 Sensor data permissions

   | Sensor                      | Permission                             | Sensitivity        | Permission Description                   |
   | ------------------------- | -------------------------------- | ------------ | ----------------------- |
   | Acceleration sensor, uncalibrated acceleration sensor, and linear acceleration sensor| ohos.permission.ACCELEROMETER    | system_grant | Allows an application to subscribe to data of these acceleration-related sensors in the motion category.|
   | Gyroscope sensor and uncalibrated gyroscope sensor         | ohos.permission.GYROSCOPE        | system_grant | Allows an application to subscribe to data of the gyroscope-related sensors in the motion category.|
   | Pedometer sensor                      | ohos.permission.ACTIVITY_MOTION  | user_grant   | Allows an application to subscribe to the motion status.               |
   | Heart rate sensor                      | ohos.permission.READ_HEALTH_DATA | user_grant   | Allows an application to read health data.               |



2. The APIs for subscribing to and unsubscribing from sensor data work in pairs. If you do not need sensor data, call the unsubscription API to stop sensor data reporting.
