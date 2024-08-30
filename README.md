# Mesure-de-Stock

## Requirements

### System Requirements

* [ROS Humble](https://docs.ros.org/en/humble/Installation.html)

* [Gazebo Garden](https://gazebosim.org/docs/garden/install)

* [Cartographer ROS](https://google-cartographer-ros.readthedocs.io/en/latest/)

* [Ubuntu 22.04](https://releases.ubuntu.com/jammy/)


### Workspace Requirements

* [Ardupilot](https://github.com/ArduPilot/ardupilot_gz)

* [Ros 2]()

* [Gazebo]()

## Installation

### Setup workspace
Follow this youtube tutorial for setup the workspace: [youtube](https://www.youtube.com/watch?v=2BhyKyzKAbM&ab_channel=XiaodiTao)

## Build

Build it with colcon build:
```bash
cd ~/ros2_ws
colcon build

```

## Usage

### 1. Launch Gazebo Rviz and Ardupilot

This simulation has an Iris copter equipped with lidar in a warefouse.
To launch rviz gazebo and ardupilot, run:

```bash
cd ~/ros2_ws
source install/setup.bash
ros2 launch ardupilot_gz_bringup iris_warehouse.launch.py
```

To launch the cartographer in rviz, run:
```bash
cd ~/ros2_ws
source install/setup.bash
ros2 ros2 launch ardupilot_ros cartographer.launch.py 
```

In another terminal, with the world and copter in place, Mavproxy:

```bash
cd ~/ros2_ws
source install/setup.bash
mavproxy.py --console --aircraft test --master :14550

```
