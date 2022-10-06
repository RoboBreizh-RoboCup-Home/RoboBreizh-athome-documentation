# How to run the project

- [How to run the project](#how-to-run-the-project)
  - [Commands to launch on the robot](#commands-to-launch-on-the-robot)
  - [Commands to run on your computer](#commands-to-run-on-your-computer)
  - [Example on how to modify and run a .launch file](#example-on-how-to-modify-and-run-a-launch-file)
- [How to run dialog module](#how-to-run-dialog-and-understand-the-workarounds)
  - [How to run it](#how-to-run-it)

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
export ROS_IP=$(ip a | sed -En 's//127.0.0.1//;s/.*inet (addr:)?(([0-9]*\.){3}[0-9]*).*/\2/p | grep 192) # IP of YOUR COMPUTER
export ROS_MASTER_URI=http://192.168.50.44:11311 # IP of the robot

# Feel free to add them to your .bashrc or .zshrc
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
export ROS_IP=192.168.50.44 # IP of the robot
export ROS_MASTER_URI=http://192.168.50.44:11311 # IP of the robot
rviz rviz
```

# How to run dialog and understand the workarounds

The dialog module uses tools of the native API NAOqi to determine the "Energy level" which is the intensity delivered by the microphones and represent the voice volume.
Using the sound level we are able to detect whenever someone speaks and record a sound buffer and write it in a .wav file.

One issue we have so far with this process is that writting it in a wav file takes too many seconds.

The process described above runs in a thread that we can not pause. The workaround we found in order to put the thread on hold when we don't need it is writting a boolean value into a database to tell weither or not we want to run the listening.

## How to run it

In 3 different terminal :
 - 1 - Run the driver
 - 2 - Start the launch file within the dialog_pepper folder
 - 3 - Open the manager database and run a SQL query to change the boolean value and start listening
```
sqlite3 ~/robobreizh_pepper_ws/src/manager_pepper/manager_db/roboBreizhDb.db 

# Run the following sql query after entering the CLI interface of the database
update dialog set run = 1 where id = 1;

```
