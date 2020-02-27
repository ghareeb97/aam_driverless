# aam_driverless

## Prerequisites
<b>- Install ROS packages:</b>
ros-kinetic-ackermann-msgs
ros-kinetic-twist-mux
ros-kinetic-joy
ros-kinetic-controller-manager
ros-kinetic-robotnik-msgs
ros-kinetic-velodyne-simulator
ros-kinetic-effort-controllers
ros-kinetic-velocity-controllers
ros-kinetic-joint-state-controller
ros-kinetic-gazebo-ros-control

```
sudo apt-get install ros-kinetic-ackermann-msgs ros-kinetic-twist-mux ros-kinetic-joy ros-kinetic-controller-manager ros-kinetic-robotnik-msgs ros-kinetic-velodyne-simulator ros-kinetic-effort-controllers ros-kinetic-velocity-controllers ros-kinetic-joint-state-controller ros-kinetic-gazebo-ros-control ros-kinetic-robotnik-msgs
```


## Steps
1-Create a workspace for the simulation if you don't have one:
```mkdir -p ~/aamfsd_ws/src```


Copy the contents of this repository to the `src` folder you just created.
Navigate to your workspace and build the simulation:


```cd ~/aamfsd_ws
catkin_make
source /devel/setup.bash
```


Choose one of theses tracks to run and replace the "empty" in the cmd below.
⋅⋅* empty
⋅⋅* acceleration
⋅⋅* skidpad
⋅⋅* sprint17
⋅⋅* small_track
⋅⋅* big_track


```roslaunch eufs_gazebo empty.launch```
To control the car open another terminal and run:
```roslaunch robot_control rqt_robot_control.launch```
To use keyboard open another terminaland run
```rosrun teleop_twist_keyboard teleop_twist_keyboard.py```


## Troubleshooting
If your recieved this error while running rqt_robot_control.launch


ERROR: cannot launch node of type [robot_control/twist_to_ackermannDrive.py]: can't locate node [twist_to_ackermannDrive.py] in package [robot_control]


Cancel the operation and run the cmds below in the same terminal 
```
roscd robot_control
chmod +x nodes/twist_to_ackermannDrive.py
```
Now rerun and have fun.
