# MicroStrain IMU (3DM-GX5-25)
## 1 Kit component
## 2 Specification

## 3 ROS2 driver
The ROS2 driver on githuub is [microstrain_inertial](https://github.com/LORD-MicroStrain/microstrain_inertial/tree/ros2).

### 3.1 Install driver
1. ```apt``` for humble
```shell
    # install using apt
    sudo apt update
    # install driver
    sudo apt install ros-humble-microstrain-inertial-driver
    # install rqt
    sudo apt install ros-humble-microstrain-inertial-rqt
```
2. ```apt``` for foxy


### 3.2 Run driver to obtain ROS2 topics
1. ros2 launch node
```shell
    ros2 launch microstrain_inertial_driver microstrain_launch.py
```
which leads to
<img title="VLP-16 Config" src="./img/imu_3dm_gx5_25/ros2_launch.png">

2. we should be able to see ros2 topics and echo them 
<img title="VLP-16 Config" src="./img/imu_3dm_gx5_25/ros2_topic_echo.png">