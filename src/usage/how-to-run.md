# How to run the project

- [How to run the project](#how-to-run-the-project)
  - [Commands to launch on the robot](#commands-to-launch-on-the-robot)
  - [Commands to run on your computer](#commands-to-run-on-your-computer)

## Commands to launch on the robot
Because ros needs to connect to the API first start nao driver in a terminal:
 - ```roslaunch naoqi_driver naoqi_driver.launch network_interface:=wlan0``` if you are in wi-fi
 - ```roslaunch naoqi_driver naoqi_driver.launch network_interface:=eth0``` if you are connected via ethernet

After, you can start in a new terminal any ros node to connect.

If you want to start a task you need to run the manager which is responsible for triggering petri plans, itself triggering ros calls to different services.

## Commands to run on your computer

Before starting a ros node on your computer you need to tell your terminal where to find the roscore which is on the robot because you started the driver beforehand.

```
export ROS_IP=192.168.50.44 // IP of the robot
export ROS_MASTER_URI=http://192.168.50.44:11311 // IP of the robot
```

In order to vizualize, the map and output from different topics. You can start Rviz a native vizualization tool provided by the ROS framework.

To start fresh run ```rviz rviz```.


If you want to start from an existing file ```rosrun rviz rviz -d [path/of/the/file]``` 