
<!-- Header with KIET Robotics logo on right -->
<table>
<tr>
<td>

## 🤖 Autonomous Navigation Robot using ROS2, SLAM Toolbox, and Nav2 -2d lidar

### (k12_description – ROS2 Simulation Package)
</td>
<td align="right" valign="top">

<img src="https://uploads.onecompiler.io/43pdbrrr7/44e9yme28/1000271448.jpg" 
alt="KIET Robotics Logo" 
width="250" 
style="border-radius: 6px;"/>

</td>
</tr>
</table>

---
A robotics project implementing **Simultaneous Localization and Mapping (SLAM)** and autonomous navigation using **ROS 2 Humble**, **slam_toolbox**, **Navigation2 (Nav2)**, **Gazebo**, and **RViz**.

This package contains the robot description, simulation setup, SLAM configuration, and full navigation stack integration for a differential drive autonomous robot.

## 📌 Overview

This project demonstrates a **Differential Drive Autonomous Navigation Robot** capable of:

* Building maps using SLAM Toolbox
* Localizing in unknown environments
* Saving and loading occupancy grid maps
* Planning and executing autonomous paths using Nav2
* Avoiding obstacles using global and local costmaps

**Robot Type:** Differential Drive
**Simulation:** Gazebo 11
**Visualization:** RViz2
**Navigation:** Nav2 Stack
**SLAM:** SLAM Toolbox

---

## 📸 Simulation & Navigation Results

### 🔹 Gazebo Simulation
<img width="100%" src="https://uploads.onecompiler.io/43pdbrrr7/44dv94y9j/Screenshot%20from%202026-02-17%2014-59-32.png" />

---
🔹 SLAM Mapping
<img width="100%" src="https://uploads.onecompiler.io/43pdbrrr7/44dv94y9j/Screenshot%20from%202026-02-17%2015-00-08.png" />

---

### 🔹 Autonomous Navigation in RViz
<img width="100%" src="https://uploads.onecompiler.io/43pdbrrr7/44dv94y9j/Screenshot%20from%202026-02-17%2015-01-27.png" />
---

## ✨ Features

### ✅ Implemented

* URDF/Xacro-based robot model
* Differential drive configuration
* Gazebo simulation environment
* RViz visualization setup
* SLAM Toolbox integration
* Map saving and loading
* Nav2 navigation stack integration
* Map server lifecycle management
* Goal-based autonomous navigation

### 🔨 In Progress

* SLAM parameter optimization
* Costmap tuning improvements
* Sensor fusion (LiDAR / Camera)
* Advanced path planning
* Dynamic obstacle avoidance

---

## 📦 Prerequisites

* Ubuntu 22.04
* ROS2 Humble Hawksbill
* Gazebo 11
* Python 3.10+

### Required ROS2 Packages

```bash
sudo apt install ros-humble-desktop
sudo apt install ros-humble-gazebo-ros-pkgs
sudo apt install ros-humble-navigation2
sudo apt install ros-humble-nav2-bringup
sudo apt install ros-humble-slam-toolbox
sudo apt install ros-humble-robot-localization
sudo apt install ros-humble-teleop-twist-keyboard
```

---

## 🚀 Installation & Build

```bash
cd ~/ros2_ws
colcon build --packages-select k12_description
source install/setup.bash
```

---

## 🎮 Usage

---

### 🔹 1. Launch Gazebo Simulation

```bash
ros2 launch k12_description gazebo.launch.py
```

---

### 🔹 2. Run SLAM (Mapping Mode)

```bash
ros2 launch k12_description online_async.launch.py mapping:=true
```

Save the map:

```bash
ros2 run nav2_map_server map_saver_cli -f ~/rover_ws/map
```

---

### 🔹 3. Run Navigation with Saved Map

```bash
ros2 launch k12_description navigation.launch.py
```

---

### 🔹 4. Launch Nav2 RViz

```bash
ros2 launch nav2_bringup rviz_launch.py
```

---

### 🔹 5. Teleoperation (Manual Control)

```bash
ros2 run teleop_twist_keyboard teleop_twist_keyboard
```

---

## 📁 Project Structure

```
k12_description/
├── config/
├── launch/
├── maps/
├── rviz/
├── urdf/
├── worlds/
├── CMakeLists.txt
└── package.xml
```

---

## ⚙️ Configuration

### Robot Parameters

Modify files inside `urdf/` to change:

* Robot dimensions
* Wheel radius
* Sensor placement
* Physical properties

### Navigation Parameters

Located inside `config/`:

* nav2_params.yaml
* slam_params.yaml
* controller_params.yaml

---

## 📝 Known Issues

* SLAM tuning improvements required
* Navigation parameter tuning ongoing
  

---

## 👩‍💻 Author

**Aishwarya Sai**
B.Tech – 3rd Year

---
## 📧 Contact

📩 **[aishsatya77@gmail.com](mailto:aishsatya77@gmail.com)**

---

