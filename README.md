# Self Driving Lab - Closing the loop at Argonne APS


## Using AWS Robomaker to get U3E robots working in simulation mode using Gazebo

The goal is to get ROS working using AWS Robomaker with a UR3E (Universal Robot) working in a Gazebo simulation mode. Next, we want to integrate EPICS/BlueSky to get data from beamline. We want to use the data from beamline streamed and determine an action based on the data and have the simulation in Gazebo updated. Subsequently, we will replace Gazebo with real robot control.

I found that AWS RoboMaker to the fastest way to setup a collaborative development environment (especially if you have a macOS laptop)

## Using AWS RoboMaker to set ROS environments for Robot development

1. Create a AWS account at [AWS](https://aws.amazon.com) using your email address
2. In the AWS console, go to RoboMaker service and click on Development environments ![create development environment](images/Robomaker1.png)

```
$ source /opt/ros/<your_ros_version>/setup.bash
$ mkdir -p catkin_ws/src && cd catkin_ws
$ git clone -b boost https://github.com/UniversalRobots/Universal_Robots_Client_Library.git \
 src/Universal_Robots_Client_Library
$ git clone https://github.com/UniversalRobots/Universal_Robots_ROS_Driver.git \
src/Universal_Robots_ROS_Driver
$ git clone -b calibration_devel https://github.com/fmauch/universal_robot.git \
src/fmauch_universal_robot
$ sudo apt update -qq
$ rosdep update
$ rosdep install --from-paths src --ignore-src -y
$ catkin_make_isolated
$ source devel_isolated/setup.bash
```

And finally

```

roslaunch ur_gazebo ur5.launch

```

![Screenshot1](images/2.png)
![Screenshot2](images/3.png)
![Screenshot3](images/4.png)
![Screenshot4](images/5.png)
![Screenshot5](images/6.png)
![Screenshot6](images/7.png)
![Screenshot7](images/8.png)
![Screenshot8](images/9.png)
![Screenshot9](images/10.png)
![Screenshot10](images/11.png)


<br>
Useful links:<br>
1. AWS Tutorial on using TurtleBot with Robomaker: https://aws.amazon.com/blogs/aws/aws-robomaker-develop-test-deploy-and-manage-intelligent-robotics-apps/ <br>
2. Removing dpkg lock: https://itsfoss.com/could-not-get-lock-error/

