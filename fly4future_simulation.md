# MRS system in simulation
Until Oct. 2025, the simulator of MRS system in fully supported by ROS noetic and partilly supported by ROS2. The suggested container is Apptainer.

Documents are available at [F4F MRS CTU Doc](https://ctu-mrs.github.io/docs/introduction).

## Trajectory generation
The pkg [Trajectory generation](https://ctu-mrs.github.io/docs/1.5.0/features/trajectory_generation/) can generate a trajectory based on input waypoints. 

We can send waypoints using a service `/uav*/trajectory_generation/path`, then make the control manager to track the generated reference trajectory.

For instance, we can call the service `/uav*/trajectory_generation/path` using
```bash
    rosservice call uav1/trajectory_generation/path mrs_msgs/Path "path:
    --Other parameters--
    points:
    - position: {x:1.0, y:0.0, z:1}
    heading: 0.0
    - position: {x:1.0, y:1.0, z:1}
    heading: 0.0
    - position: {x:0.0, y:1.0, z:1}
    heading: 0.0
    - position: {x:0.0, y:0.0, z:1}
```
which should generate a square trajectory from `current_position --> (1,0,1) --> (1,1,1) --> (0,0,1) --> (0,0,1)`. Then we need to use control manager to begin the tracjectory tracking with
```bash
    rosservice call /uav1/control_manager/start_trajectory_tracking
```
## Precise landings
