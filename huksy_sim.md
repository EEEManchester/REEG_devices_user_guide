# Set clearpath and UAV simulation in RO2 Humble

### 1. Clearpath in ROS2 humble
```shell
    ros2 launch clearpath_gz simulation.launch.py
```
NOTE: we must click "start" within 3-4 seconds/

Commands to test
```shell
    ros2 topic pub /a200_0000/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 2.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.0}}"
```
We can use teleop_twist_keyboard to control the robot with keyboard. Only thing to be carefly is to map topics to the one set by clearpath.
```shell
  ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args --remap cmd_vel:=a200_0000/cmd_vel
```
### 1.2 choose different robots
We can use different clearpath robots by modifying robot.yaml file in ```~/clearpath```. An example is given as bellow:
```yaml
  ros2:
    namespace: a200_0000
    domain_id: 0
    middleware:
      implementation: rmw_fastrtps_cpp
    workspaces: 
    - /home/mscroboticslaptop19/clearpath_ws/install/setup.bash 
```

Then, we need to regenerate robot simulation files.
```shell
    ros2 run clearpath_generator_common generate_bash -s ~/clearpath
    source ~/clearpath/setup.bash
```

## 2. SLAM with clearpath
### 2.1 Install slam-toolbox
```shell
    sudo apt install ros-humble-slam-toolbox
```
### 2.2 SLAM with clearpath

1. run simulation 
```shell
  ros2 launch clearpath_gz simulation.launch.py
```

2. view in rviz 
```shell
  ros2 launch clearpath_viz view_navigation.launch.py namespace:=a200_0000
```


3. run SLAM_toobox
```shell
   ros2 launch clearpath_nav2_demos slam.launch.py setup_path:=$HOME/clearpath/ use_sim_time:=true
```

4. use keyboard control to move robot everwhere to build a map
```shell
  ```shell
  ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args --remap cmd_vel:=a200_0000/cmd_vel
```

rqt_grap about slam is 


## 3. Localisation with clearpath



## 4. path planning with clearpath