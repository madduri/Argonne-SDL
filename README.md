# Argonne-SDL


Using AWS Robomaker to get U3E working. The goal is to get ROS working using AWS Robomaker with a UR3E (Universal Robot) working in a Gazebo simulation mode. Next, we want to integrate EPICS/BlueSky to get data from beamline. We want to use the data from beamline streamed and determine an action based on the data and have the simulation in Gazebo updated. Subsequently, we will replace Gazebo with real robot control.

Open issues:

Communication between real robot and the service

Building a Ur3E driver to load into RoboMaker: https://github.com/ros-industrial/universal_robot

## Using AWS Robomaker to set ROS environments for Robot development

1. Create a AWS account at [AWS](https://aws.amazon.com) using your email address
2. In the AWS console, click on AWS Robomaker ![images/Robmaker1.png]

```
$ source /opt/ros/<your_ros_version>/setup.bash

```
$ mkdir -p catkin_ws/src && cd catkin_ws
$ git clone -b boost https://github.com/UniversalRobots/Universal_Robots_Client_Library.git src/Universal_Robots_Client_Library
$ git clone https://github.com/UniversalRobots/Universal_Robots_ROS_Driver.git src/Universal_Robots_ROS_Driver
$ git clone -b calibration_devel https://github.com/fmauch/universal_robot.git src/fmauch_universal_robot
$ sudo apt update -qq
$ rosdep update
$ rosdep install --from-paths src --ignore-src -y
$ catkin_make_isolated
$ source devel_isolated/setup.bash


roslaunch ur_gazebo ur5.launch


Useful links:
1. AWS Tutorial on using TurtleBot with Robomaker: https://aws.amazon.com/blogs/aws/aws-robomaker-develop-test-deploy-and-manage-intelligent-robotics-apps/
2. Removing dpkg lock: https://itsfoss.com/could-not-get-lock-error/

