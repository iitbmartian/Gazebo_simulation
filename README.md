# Gazebo Simulations
The following Repo contains Gazebo Simulations of IITB Mars Rover Team.

## Instructions for ROS and Gazebo installations
1. ROS kinetic and Gazebo-7 is used.
2. Follow instructions on `https://wiki.ros.org/kinetic/Installation/Ubuntu`
3. Opt for `ros-kinetic-desktop-full` installation

## Building the catkin-packages
1. Follow the steps to build the provided packages
```bash
 mkdir -p rover_ws/src
 cd rover_ws/src
 git clone https://github.com/iitbmartian/GUI_MSI_2016 CHANGE
 cd ..
 catkin_make

```
2. Replace `line 15` and `line 29` of `rover_18/gazebo_worlds/terrain.world` with `<mesh><uri>PATH_TO_YOUR_WORKSPACE/rover_ws/src/rover_18/gazebo_worlds/terrain_surface/surface1.stl</uri></mesh>`.
3. Replace `line 33` of `rover_18/gazebo_worlds/terrain.world` with `<uri>PATH_TO_YOUR_WORKSPACE/rover_ws/src/rover_18/gazebo_materials/scripts/terrain.material</uri>`.


## Visualisation of Rover on RViz
* Execute `roslaunch rover18_urdf rviz.launch`

## Gazebo Simulation
1. To load the rover in a defined world execute `roslaunch rover18_urdf gazebo.launch`
2. For Simulating differential-drive in the world execute `roslaunch rover18_urdf diff_drive.launch`. Control the speed and direction of rover using `rqt_robot_steering` node launched. 
3. The forces in links can be viewed on `gz topic`. 
4. For changing the worlds edit the world names in `rover_18/launch/gazebo.launch` `line 18`

## Example Video

Take a look at some simulations in `https://drive.google.com/drive/folders/1oUSBbVFecmz7PkJIKtDzw7NwfP6030fT?usp=sharing`

## Additional Softwares used 
1. Blander Sculpt tool - To create the Custom terrain
2. `[3DView](https://chrome.google.com/webstore/detail/3dview/hhngciknjebkeffhafnaodkfidcdlcao?hl=en)` - To edit stl meshes and evaluate translation and rotation coordinates of joints/links.

## Packages used
1. `[gazebo_ros_control](http://gazebosim.org/tutorials?tut=ros_control)` to implement differential control on the rover
2. `[rqt_robot_steering](http://wiki.ros.org/rqt_robot_steering)` for UI to control rover movement
3. `[force_torque_sensor](http://gazebosim.org/tutorials?tut=force_torque_sensor&cat=sensors)` to get the forces in joints