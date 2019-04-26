# Philos Project

(description of this project goes here)

## Current Project State

### Robot configuration description is stored under the "urdf" folder:

The "joints_transmissions.xacro" defines a macro for automatically populating some redundant information when a revolute joint is created. The hardware_interface/PositionJointInterface needs to be double checked to work with the specific motors on the robot. (more details at http://wiki.ros.org/ros_control)

"philos_urdf.xacro" creates the robot models in Rviz and Gazebo. The visual elements are STL files exported from Solidworks, and the collision models are simplified geometric models that oversize the STL for simpler collision checks. The visual origin values are unimportant and are for visualization only; Link collision properties need to be checked upon every redesign of the mechanism; Joint limits properties need to match the actual motor's specifications. The inertial properties are not to be trusted, and should be updated once the mechanism design and CAD model are finalized.

"Model Construction Description" gives a more intuitive description of where each link/joint is connected.

### Robot CAD models are stored under the "meshes" folder:

These files are oversimplified CAD for visualization of the robot only.

### Robot joint controller parameters are stored under the "config" folder:

"joints.yaml" specifies the type of controller used for each joint. Currently they are all position_controllers/JointPositionController, and they need to match the motors used. (more details at http://wiki.ros.org/ros_control)

### Simulation launch files

To launch Rviz only for easier robot configuration changes

```bash
roslaunch philos rviz.launch
```

To launch Gazebo with Rviz
```bash
roslaunch philos spawn.launch
```
