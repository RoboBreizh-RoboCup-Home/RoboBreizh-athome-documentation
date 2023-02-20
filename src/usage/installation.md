## Contents

- [Installation](#installation)
  - [Install every package](#install-every-package)
  - [Maintain robobreizh_pepper_ws](#maintain-robobreizh_pepper_ws)

# Installation

The file architecture is set up to be a ros workspace.

```
├── README.md
├── src
│   ├── CMakeLists.txt
│   ├── dialog_pepper
│   ├── manager_pepper
│   ├── manipulation_pepper
│   ├── navigation_pepper
│   ├── pepper_naoqi_ros
│   ├── perception_pepper
│   └── tablet_pepper
└── updateGitSubmodules.sh
```

## Install every package

If you want to install all the modules your can download the robobreizh_pepper_ws

This repository is built upon differents submodules. The current architecture is:
All submodules can be cloned independantly:

- robobreizh_navigation: see the [original repository](https://github.com/RoboBreizh-RoboCup-Home/navigation_pepper).
- robobreizh_dialog: see the [original repository](https://github.com/RoboBreizh-RoboCup-Home/dialog_pepper).
- robobreizh_perception: see the [original repository](https://github.com/RoboBreizh-RoboCup-Home/perception_pepper).
- robobreizh_manipulation : see the [original repository](https://github.com/RoboBreizh-RoboCup-Home/manipulation_pepper).
- robobreizh_manager : see the [original repository](https://github.com/RoboBreizh-RoboCup-Home/manager_pepper).
- pepper_naoqi_ros : see the [original repository](https://github.com/Maelic/pepper_naoqi_ros.git)

1. clone the repository:

```buildoutcfg
git clone --recursive https://github.com/RoboBreizh-RoboCup-Home/robobreizh_pepper_ws.git
git submodule update --init --recursive
```

2. Install the dependencies

```buildoutcfg
cd robobreizh_pepper_ws
chmod +x ./src/pepper_naoqi_ros/install.sh && ./pepper_naoqi_ros/install.sh
```

3. Build the workspace

```buildoutcfg
# if you are using bash terminal
catkin_make && source devel/setup.bash
```

```buildoutcfg
# if you are using zsh terminal
catkin_make && source devel/setup.zsh
```

## Maintain robobreizh_pepper_ws

If you want to pull only one submodule you can by using:

```buildoutcfg
git submodule update <specific path to submodule>
```

If you want to update the whole main repository

```bash
chmod +x updateGitSubmodules.sh && ./updateGitSubmodules.sh
or
git submodule foreach git pull
---
git add .
git commit -m [insert commit message like usual]
```
