# RB1 ROS2 Integration

# Introduction
This package makes integrating controlling the RB1 robot easier by using ROS2 Control Framework. It includes Differential drive and elevator usage.

# Installation

Download the git repository
cd ~ros2_ws/src

git clone https://github.com/Hamz115/rb1_ros2_description.git

cd ~ros2_ws

colcon build

source install/setup.bash

After compiling we are ready to integrate It

# Launch
Launch the simulation using this command

ros2 launch rb1_ros2_description rb1_ros2_xacro.launch.py

Please give it a second to load properly

Next we activate the controllers

# Controllers
ros2 control list_hardware_interfaces

ros2 control list_controllers

##### Can use this command to control robot motion

ros2 topic pub --rate 10 /diffbot_base_controller/cmd_vel_unstamped geometry_msgs/msg/Twist "{linear: {x: 0.2, y: 0, z: 0.0}, angular: {x: 0.0,y: 0.0, z: 0.3}}"

# Elevator
For using the elevatoruse these commands

ros2 service call /apply_joint_effort gazebo_msgs/srv/ApplyJointEffort '{joint_name: "robot_elevator_platform_joint", effort: 1.0, start_time: {sec: 0, nanosec: 0}, duration: {sec: -1, nanosec: 0} }'

ros2 service call /apply_joint_effort gazebo_msgs/srv/ApplyJointEffort '{joint_name: "robot_elevator_platform_joint", effort: -1.0, start_time: {sec: 0, nanosec: 0}, duration: {sec: -1, nanosec: 0} }'

## ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Phase 2: Strengthen Your Robotics Programming Skills - Section 15 : ROS2 Control
## Checkpoint 15: ROS2 Control
##### Description - This checkpoint is about integrating ROS2 Control with the RB1 Robot
##### Score - 9.3/10
##### Attempts - 1
