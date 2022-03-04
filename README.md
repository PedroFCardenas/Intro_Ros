# Robotics - UNAL - LAB2
## Requirements
Modern robotics relies in the versatile middleware know as ROS (Robotic Operative System). Some of the most useful tools in robotics run in this framework. Learning ROS could lead to insanity (jikes...) but fortunaly with time and patience (tons of), all of you young padawans will master the power of ROS.

### Linux
**ROS runs on linux, period.**

There are a couple of ways to run Linux:
- Native instalation (Recommended, almost mandatory)
- Virtual machine (Almost everything works, but intensive gpu apps will crash)
- Docker (Too new)
- Linux substrate for windows (Fancy, but it has some compatibility issues, a it has no GUI)

For this course the Linux of choice is [Ubuntu 20.04 LTS](https://ubuntu.com/download/desktop "Ubuntu 20.04 LTS"). In this [link](https://www.tecmint.com/install-ubuntu-20-04-desktop/ "link") you will find a good installation tutorial.
### ROS
Once linux has been installed, it's ROS time. For this course ROS Noetic will be used. The installation steps for ubuntu are [here](http://wiki.ros.org/noetic/Installation/Ubuntu "here"), for other Linux distros look [here](http://wiki.ros.org/noetic/Installation "here").

In any case, I left the instructions in this repo as well. Just open a new terminal an run the followging commands:

```console
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt install curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo apt update
sudo apt install ros-noetic-desktop-full
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
sudo apt install python3-rosdep
sudo rosdep init
rosdep update
```
Please visit the [Frobs_RL](https://github.com/jmfajardod/frobs_rl "Frobs_RL") repo, leave a star and salute FajardROS (One of the only few guys that has master ROS).

### Recommended apps/packages
After yers of trying learning ROS I have compiled some useful tools, some of them have been suggestions, some have been my own discovery.

#### VSCode
Thanks to Microsoft for one of the best code editors in the world. I strongly recommend it. [Here](https://code.visualstudio.com/docs/setup/linux "Here") there is the official way to install VScode on Ubuntu.

#### Kitty
Linux terminal is really powerfull, when you master the shell you are gonna look kinda hackerish. Nonetheless, the defult terminal in Ubuntu could be constrained. FajardROS found Kitty, since the I started loving cats. [Link](https://sw.kovidgoyal.net/kitty/binary/ "Link") to official page, and link for the installation [guide](https://connectwww.com/how-to-install-kitty-on-ubuntu-kitty-terminal-emulator/61186/ "guide").

#### Catkin build
Once you install ROS you realize that catkin is package compiler (kinda). *catkin_make* compiles the entire workspace, there is no harm if you hace a couple of light packges, but if you have a lot of packges in one workspace, I recommend you to install *catkin_build*. It will allow to compile the packages separately. Open a terminal (hopefully kitty) and run:

```console
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu `lsb_release -sc` main" > /etc/apt/sources.list.d/ros-latest.list'
wget http://packages.ros.org/ros.key -O - | sudo apt-key add -
sudo apt-get update
sudo apt-get install python3-catkin-tools
```

### Git
If you are reading this, you will probably have some experience with repositories,  in the case you do not have it in your machine, just open a terminal and run:

```console
sudo apt update
sudo apt install git
git --version
```
## Python and C++
Fortunately python3 interpreter and C compiler are preinstalled on linux, so no worries it is no Windows.

------------

If I found more tools, I will add them here. If you find someting interesting don't hesitate of letting me know.

------------

## Turtlesim

Now the real businesses.

Clone the *hello_turtle* repo from [here](https://github.com/felipeg17/hello_turtle). It's a sort of hello world in the ROS community. Some changes have been added, but don't worry, during the class you will learn most of the concepts.

##### Run ROSCORE and Turtlesim_node
First open 3 terminals (if you use Kitty press ctrl + shift + enter trhee times) and run:
**First terminal**
```console
roscore
```
**Second terminal**
```console
rosrun turtlesim turtlesim_node
```
![alt text](https://i.postimg.cc/j2TbKyPc/Screenshot-from-2022-03-04-12-10-27.png)

You will get someting like this:
![alt text](https://i.postimg.cc/FsD45dRb/Screenshot-from-2022-03-04-12-10-50.png)
If you are lucky enough, you will get a better turtle icon than me.

##### Nodes and Topics
In the third terminal run:
**Third terminal**
```console
rostopic list
rosnode list
```
![alt text](https://i.postimg.cc/bwrjzyD7/Screenshot-from-2022-03-04-12-11-17.png)

You will see all topics and nodes running. Notice that the topics related with the turtle simulation have the */turtle1* namespace.

Now in the same terminal run:
**Third terminal**
```console
rosrun turtlesim turtle_teleop_key
```
It will allow you to move the turtle around using the keys.

Open a new terminal and run:
**Fourth terminal**
```console
rqt_graph
```
![alt text](https://i.postimg.cc/0NJRwVCZ/Screenshot-from-2022-03-04-12-13-44.png)
A graphical visualization of the topics and nodes will apper, It shows the interconnections between them.



