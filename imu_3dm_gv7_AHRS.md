# MicroStrain IMU (3DM-GV7-AHRS)
## 1 Kit component
Author: zhongmou.li@manchester.ac.uk

**Kit**
- MicroStrain 3DM-GV7-AHRS  
- Wire with a USB port provided by MicroStrain
<img title="VLP-16 Config" src="./img/imu_3dm_gx5_gv7/gv7_kit.jpg">

**Host machine**
- Ubuntu 22.04
- ROS2 Humble

## 2 Specification
A 9-axis IMU module that provides measurements of linear acceleration, angular rate and attitude. 

Datasheet can be found at [MicroStrain 3DM-GX5-AHRS](https://www.microstrain.com/inertial-sensors/3dm-gx5-25).

Some important information is listed here:
- Attitude
    - Attitude Frequency: 1 - 1000 Hz
    - Static Roll/Pitch Accuracy: 0.25°
	- Dynamic Roll/Pitch Accuracy: 0.5°
	- Static Heading (AHRS only): 0.5°
	- Dynamic Heading (AHRS only): 2°

- Accelerometer 
    - Resolution: not given clearly
    - Sampling rate: 1 kHz  
- Gyroscope 
    - Resolution: not given clearly
    - Sampling rate: 1000 Hz 

## 3 Install and run ROS2 driver
The ROS2 driver on githuub is [microstrain_inertial](https://github.com/LORD-MicroStrain/microstrain_inertial/tree/ros2).