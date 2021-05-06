# Argonne-SDL


Using AWS Robomaker to get U3E working. The goal is to get ROS working using AWS Robomaker with a UR3E (Universal Robot) working in a Gazebo simulation mode. Next, we want to integrate EPICS/BlueSky to get data from beamline. We want to use the data from beamline streamed and determine an action based on the data and have the simulation in Gazebo updated. Subsequently, we will replace Gazebo with real robot control.

Open issues:

Communication between real robot and the service

Building a Ur3E driver to load into RoboMaker:

https://github.com/ros-industrial/universal_robot

ISSUES: Removing dpkg lock: https://itsfoss.com/could-not-get-lock-error/

Useful links: https://aws.amazon.com/blogs/aws/aws-robomaker-develop-test-deploy-and-manage-intelligent-robotics-apps/
