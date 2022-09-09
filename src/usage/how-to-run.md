# How to run the project

- [How to run the project](#how-to-run-the-project)
  - [Commands to launch on the robot](#commands-to-launch-on-the-robot)
  - [Commands to run on your computer](#commands-to-run-on-your-computer)
  - [Example on how to modify and run a .launch file](#example-on-how-to-modify-and-run-a-launch-file)

## Commands to launch on the robot
Because ros needs to connect to the API first start nao driver in a terminal:
 - ```roslaunch naoqi_driver naoqi_driver.launch network_interface:=wlan0``` if you are in wi-fi
 - ```roslaunch naoqi_driver naoqi_driver.launch network_interface:=eth0``` if you are connected via ethernet

After, you can start in a new terminal any ros node to connect.

If you want to start a task you need to run the manager which is responsible for triggering petri plans, itself triggering ros calls to different services.
Because we have different settings for the tasks we set a variable that tells us what to trigger.
Following are the possible task to execute
  - find_my_mates
  - receptionist
  - restaurant
  - gpsr
  - store_groceries

```
roslaunch manager_pepper robobreizh_manager.launch [taskname]:=true door:=true|false
```

## Commands to run on your computer

Before starting a ros node on your computer you need to tell your terminal where to find the roscore which is on the robot because you started the driver beforehand.

```
export ROS_IP=192.168.50.44 // IP of the robot
export ROS_MASTER_URI=http://192.168.50.44:11311 // IP of the robot
```

In order to vizualize, the map and output from different topics. You can start Rviz a native vizualization tool provided by the ROS framework.

To start fresh run ```rviz rviz```.


If you want to start from an existing file ```rosrun rviz rviz -d [path/of/the/file]``` 

## Example on how to modify and run a .launch file

**Terminal 1: start driver**
```
ssh nao@pepper2.local 
nao_driver
```

**Terminal 2: copy and run launch file**
```
scp perception.launc nao@pepper2.local:~/robobreizh_pepper_ws/src/perception_pepper/launch
ssh nao@pepper2.local
roslaunch perception_pepper perception.launch finals:=true
```

**Terminal 3: start rviz**
```
export ROS_IP=192.168.50.44 // IP of the robot
export ROS_MASTER_URI=http://192.168.50.44:11311 // IP of the robot
rviz rviz
```