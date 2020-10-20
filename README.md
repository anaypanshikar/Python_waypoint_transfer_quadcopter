# Python_waypoint_transfer_quadcopter
Transferring waypoints of the path to be followed to the autopilot flight controller via python code. The procedure for performing a Gazebo simulation is shown.

**System:**
- Ubuntu 18.04

**Dependencies:**
- ROS melodic
- Gazebo 9 simulator
- MAVROS
- QGroundControl (Ground Control Station software)
- Firmware repository of PX4
- Python 2

1. Start the ROS in one terminal.
```
roscore
```
2. In a new terminal, launch MAVROS by specifying the fcu_url and the gcs_url. For performing a simulation on Gazebo, just specifying the fcu_url as local host is enough.
```
roslaunch mavros px4.launch fcu_url:="udp://:14540@127.0.0.1:14557"
```
3. Navigate to the ‘Firmware’ repository of Pixhawk and enter the command to launch a quadcopter in the Gazebo simulator.
```
cd Firmware
make px4_sitl gazebo
```
![Gazebo](https://dev.px4.io/v1.10/assets/simulation/gazebo.png)

4. Navigate to the python file which contains the code for running the mission by following the specified set of waypoints and run it (name of file is waypts.py).
```
python waypts.py
```
5. Open QGC and arm the vehicle.

![QGC](https://docs.qgroundcontrol.com/master/assets/fly/arm.jpg)
