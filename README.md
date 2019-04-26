# Philos Project
This folder contains three sub-folders that contain ROS packages for simulating the Philos robot. These packages were only tested on Ubuntu 16.04 with ROS Kinetic. 
You will need to clone this entire folder to your ROS workspace and compile in order to use them. To install ROS and set up a workspace, check out my [setup script](https://github.com/YanzhouWang/ros-kinetic-moveit-setup).
You will also need the [Eigen](http://eigen.tuxfamily.org/index.php?title=Main_Page) library in order to compile. Note that the library folder name needs to be changed to **Eigen** otherwise the catkin will throw you an error.
Please read on before you attempt to compile.

## gazebo_ros_pkgs
This package is required for simulation in *Gazebo*.

## philos
This package contains a complete robot description as well as elementary *roscontrol* parameters for a basic simulation in *Gazebo* and *RViz*
The two launch files, *spawn.launch* and *rviz.launch* can be used.

## philos_moveit_config
This package contains motion planning simulation of the robot with *MoveIt!*. You will need to install *MoveIt!* onto your system by using `sudo apt-get install ros-kinetic-moveit`. 
The robot description is exactly the same as in the *philos* package.
You will likely encounter error upon compilation saying the *eigen* library is not found. That is because *MoveIt!* will try to find the library by referring it to *eigen3*. To address this error, simply use your favorite text editor and replace *eigen3* with *Eigen*. You may have to repeat this for a couple of times in order to successfully compile this package.

# Usage
Once you have ROS, *MoveIt!*, and Eigen installed and configured,
```
roscd
cd ./src
git clone https://github.com/YanzhouWang/philos_project.git
roscd
catkin_make
```
To get the best result, make sure to check out my [robot_kinematics](https://github.com/YanzhouWang/robot_kinematics) program and do some calculations before make any design changes in the robot description.
