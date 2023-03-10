# Content

- [Requirements](#requirements)
- [Installation](#installation)
- [Packages](#packages)

## Requirements

Important dependancies to have on your system are version controllers.

- git : Make sure to know how to use git and have it installed on your computer
- gh : cli tool for gh authentification and others [link](https://github.com/cli/cli/blob/trunk/docs/install_linux.md)
- vcs : ros cli tool to import packages [link](https://github.com/dirk-thomas/vcstool)

Docker should also be installed on your system [link](https://docs.docker.com/engine/install/ubuntu/)

Make sure to have ROS noetic installed if you have ubuntu 20 [link](http://wiki.ros.org/noetic/Installation/Ubuntu)

You should already have VSCode with the remote containers plugin installed on your system.

- [vscode](https://code.visualstudio.com/)
- [vscode remote containers plugin](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)

## Installation

For more details you can look at the [ws repo](https://github.com/RoboBreizh-RoboCup-Home/robobreizh_pepper_ws) and the different branches

```bash
# clone and open the project
git clone https://github.com/RoboBreizh-RoboCup-Home/robobreizh_pepper_ws.git
code robobreizh_pepper_ws
```

Now that you've cloned your repo onto your computer, you can open it in VSCode (File->Open Folder).

When you open it for the first time, you should see a little popup that asks you if you would like to open it in a container. Say yes!

![template_vscode](https://user-images.githubusercontent.com/6098197/91332551-36898100-e781-11ea-9080-729964373719.png)

If you don't see the pop-up, click on the little green square in the bottom left corner, which should bring up the container dialog

![template_vscode_bottom](https://user-images.githubusercontent.com/6098197/91332638-5d47b780-e781-11ea-9fb6-4d134dbfc464.png)

In the dialog, select "Remote Containers: Reopen in container"

VSCode will build the dockerfile inside of `.devcontainer` for you. If you open a terminal inside VSCode (Terminal->New Terminal), you should see that your username has been changed to `ros`, and the bottom left green corner should say "Dev Container"

![template_container](https://user-images.githubusercontent.com/6098197/91332895-adbf1500-e781-11ea-8afc-7a22a5340d4a.png)

- Use vcs to import or update repos

```bash
vcs import < src/robobreizh.repos src
vcs pull src
```

- Setup the workspace

```bash
./setup.sh
```

- Compile the workspace

```bash
cm # this is an alias in the .zshrc file that you can find under .devcontainer/.zshrc
```

## Packages

This repository is built upon differents packages.
All submodules can be cloned independantly:

- robobreizh_navigation: see the [original repository](https://github.com/RoboBreizh-RoboCup-Home/navigation_pepper).
- robobreizh_dialog: see the [original repository](https://github.com/RoboBreizh-RoboCup-Home/dialog_pepper).
- robobreizh_perception: see the [original repository](https://github.com/RoboBreizh-RoboCup-Home/perception_pepper).
- robobreizh_manipulation : see the [original repository](https://github.com/RoboBreizh-RoboCup-Home/manipulation_pepper).
- robobreizh_manager : see the [original repository](https://github.com/RoboBreizh-RoboCup-Home/manager_pepper).
- pepper_naoqi_ros : see the [original repository](https://github.com/Maelic/pepper_naoqi_ros.git)
- tablet_pepper : see the [original repository](https://github.com/RoboBreizh-RoboCup-Home/tablet_pepper.git)
