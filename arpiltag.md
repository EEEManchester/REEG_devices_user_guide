# AprilTag
## 1 Kit components
Author: zhongmou.li@manchester.ac.uk

**Kit**

**Host machine**
- Ubuntu 22.04
- ROS2 Humble

**Pkg**
One of the two
  - CPU-based **april_ros** from [christianrauch/apriltag_ros](https://github.com/christianrauch/apriltag_ros).
  - GPU-based **isaac_ros_apriltag** from [NVIDIA-ISAAC-ROS/isaac_ros_apriltag](https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_apriltag)
- apriltag-mgs **apriltag_msgs** from [christianrauch/apriltag_msgs](https://github.com/christianrauch/apriltag_msgs)   
- 
**Reference**
- https://automaticaddison.com/autonomous-docking-with-apriltags-using-nav2-ros-2-jazzy/
- 

## 2 Install apriltag_ros 
1. obtain source code
   ```bash
    cd ros2_ws/src
    git clone https://github.com/christianrauch/apriltag_msgs
    git clone https://github.com/christianrauch/apriltag_ros
   ```

2. install dependency pkgs for apriltag
   ```bash
    cd ros2_ws/src
    rosdep update
    rosdep install --from-paths src --ignore-src -r -y
   ```

3. build the pkg **apriltag_ros**
   ```bash
    cd ros2_ws
    colcon build
   ```
