# DSP-navigation: Dynamic Social Planner navigation

## Dependencies
* Social Force Model library
```
cd /usr/local/include
sudo git clone https://github.com/robotics-upo/lightsfm.git
cd lightsfm
sudo make
sudo make install
```
* 
```
sudo apt-get update
sudo apt-get install liblcm-dev
sudo apt-get install ros-noetic-controller-interface ros-noetic-gazebo-ros-pkgs ros-noetic-gazebo-ros-control ros-noetic-joint-state-controller ros-noetic-effort-controllers ros-noetic-joint-trajectory-controller ros-noetic-realsense2-camera ros-noetic-amcl ros-noetic-move-base ros-noetic-slam-gmapping ros-noetic-hector-slam ros-noetic-map-server ros-noetic-global-planner ros-noetic-dwa-local-planner
```

## Installation
1. Clone GitHub Repositories:

```
cd
git clone https://github.com/iminolee/dsp-navigation.git
```
2. Build Workspace :
```
cd dsp-navigation
catkin_make
source devel/setup.bash
```

## Simulation Setup
![Hospital_env_preview](img/hospital_env_preview.png)
![Gazebo_scene](img/gazebo_scene.png)

## Running
1. Spawn Unitree Go1 quadruped robot into Hospital Environment at the starting location:
```
roslaunch gazebo_simulator main.launch
```
2. To use the keyboard controller **(optional)**:
```
rosrun unitree_guide junior_ctrl
```
After starting the controller, the robot will lie on the environment of the simulator, then press the '2' key on the keyboard to swith the robot's finite state machine(FSM) from Passive(initial state) to FixedStand, then press '4' key to switch the FSM from FixedStand to Trotting

Now you can press the 'W', 'A', 'S', 'D' keys to control the translation of the robot, and press the 'J', 'L' keys to control the rotation of the robot. Press the 'Spacebar', the robot will stop and stand on the ground.

The full list of transitions between states available is the following:
* Key '1': FixedStand/FreeStand to Passive
* Key '2': Passive/Trotting to FixedStand
* Key '3': Fixed stand to FreeStand
* Key '4': FixedStand/FreeStand to Trotting
* Key '5': FixedStand to MoveBase
* Key '8': FixedStand to StepTest
* Key '9': FixedStand to SwingTest
* Key '0': FixedStand to BalanceTest
