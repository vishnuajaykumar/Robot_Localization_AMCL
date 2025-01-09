# 🗺️ AMCL Localization Project

Welcome to the AMCL Localization Project, where robots localize themselves in a pre-defined map using Adaptive Monte Carlo Localization (AMCL).

# 📦 Project Overview

This project demonstrates how to localize a robot in a known environment using sensor data and odometry with the AMCL package. The robot is simulated in Gazebo and uses sensors for localization.

# 🛠️ Prerequisites

Required Tools

ROS 1 
Gazebo (default with ROS Noetic)

catkin tools: Install with:
sudo apt install python3-catkin-tools

Additional ROS packages:
sudo apt install ros-noetic-map-server \
                 ros-noetic-amcl \
                 ros-noetic-move-base \
                 ros-noetic-rviz \
                 ros-noetic-gazebo-ros

# 🏗️ How to Clone and Run

git clone https://github.com/vishnuajaykumar/Robot_Localization_AMCL.git
cd amcl_robot_project

# Build the Workspace

catkin_make
source devel/setup.bash

# Launch the localization stack with the AMCL node:

roslaunch ball_chaser amcl_navigation.launch

## 🗂️ Project Directory Structure

```
bamcl_robot_project/                   
├── src/                      
│   ├── my_robot/             
│   │   ├── launch/             # Launch files
│   │   ├── urdf/               # Robot description files
│   │   ├── world/              # Gazebo world files
│   │   ├── CMakeLists.txt      # Build configuration
│   │   ├── package.xml         # ROS package metadata
│   ├── ball_chaser/          
│   │   ├── launch/             # AMCL launch files
│   │   ├── config/             # Configuration files (costmaps, AMCL parameters)
│   │   ├── maps/               # Generated maps
│   │   ├── CMakeLists.txt      # Build configuration
│   │   ├── package.xml         # ROS package metadata
├── build/                      # Build artifacts (do not commit)
├── devel/                      # Development space (do not commit)
```

---

# 🧠 How It Works

🗺️ Map Server

The Map Server node loads a pre-defined map and provides it for localization.
For Defining yourown custom Map : Use this package 
git clone https://github.com/udacity/pgm_map_creator.git

# 🧠 AMCL Localization

Adaptive Monte Carlo Localization uses:

Laser scan data to estimate the robot’s position relative to the map.
Odometry to refine the pose estimate.
Dynamically adjusts the number of particles.
