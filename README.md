# Arm_Robot_-G-Bot-
# Semi-Humanoid Robot Joint Control Simulation (ROS 2 + Gazebo)

This repository contains a ROS 2-based simulation for a **semi-humanoid robot**, focusing on controlling three specific joints: `R_J5`, `R_J4`, and `R_J1`. The simulation utilizes **Gazebo** for physics-based visualization and **RViz** with **Joint State Publisher** for interactive testing.

---

## Features

- Simulated control of upper limb joints:
  - `R_J1`: Shoulder Joint
  - `R_J4`: Elbow Joint
  - `R_J5`: Wrist Joint
- Position control for all joints
- Launch files to:
  - Simulate in Gazebo
  - Command joint angles
  - Visualize in RViz

---

## Repository Structure

       Arm_Robot_-G-Bot-/
        ├──arm_robot/
        │ ├── config/
        │ │ └── controller_position.yaml
        │ ├── description/
        │ │ ├── Assembly.gazebo
        │ │ ├── Assembly.trans
        │ │ ├── Assembly.xacro
        │ │ ├── Assembly2.xacro
        │ │ ├── gazebo_control.xacro
        │ │ ├── inertial_macros.xacro
        │ │ ├── materials.xacro
        │ │ ├── robot.urdf.xacro
        │ │ └── robot_core_lr.xacro
        │ ├── img/
        │ │ └── lr.png
        │ ├── launch/
        │ │ ├── control.launch.py
        │ │ ├── launch_sim.launch.py
        │ │ ├── rsp.launch.py
        │ │ └── rviz.launch.py
        │ ├── meshes/
        │ │ ├── base_link.stl
        │ │ ├── left_socket_1_1.stl
        │ │ ├── link1_left_1_1.stl
        │ │ ├── link1_right_1_1_1.stl
        │ │ ├── link2_left_1_1.stl
        │ │ ├── link2_right_1_1.stl
        │ │ ├── link3_left_1_1_1.stl
        │ │ ├── link3_right_1_1_1.stl
        │ │ ├── right_socket_1_1.stl
        │ │ ├── shoulder_left_1_1_1.stl
        │ │ ├── shoulder_right_1_1_1.stl
        │ │ └── torso_1_1_1.stl
        │ ├── rviz/
        │ │ └── default.rviz
        │ ├── src/
        │ │ └── control.py
        │ ├── CMakeLists.txt
        │ ├── LICENSE
        │ ├── package.xml
        │ └── README.md
        │
        │
        │
    
---

## Dependencies

  - ROS 2 (Humble or compatible version)
  
  - Gazebo (Fortress/Garden)
  
  - Joint State Publisher GUI
  
  - RViz2
  
  - ros2_control and gazebo_ros2_control

---

## To-Do

  - Add launch arguments for custom joint limits

  - Implement trajectory control

  - Add more joints for full arm motion

### Step-by-Step Instructions

1. Navigate to your ROS 2 workspace source directory

       cd ~/ros2_ws/src

  Replace ros2_ws with your actual workspace name if different.

2. Clone the package from GitHub

       git clone https://github.com/NanduGopakumarG/Arm_Robot_-G-Bot-.git
   
4. Install any dependencies
   
From the root of your workspace:

      cd ~/ros2_ws
      rosdep install --from-paths src --ignore-src -r -y
    
This installs missing dependencies listed in the package.xml files.

4. Build the workspace

       colcon build
   
5. Source the setup file

       source install/setup.bash
   
6. You can add it to your .bashrc to make it persistent:

       echo "source ~/ros2_ws/install/setup.bash" >> ~/.bashrc
       source ~/.bashrc
    
Notes

- Make sure the package you clone has a proper package.xml and CMakeLists.txt (i.e., it’s a valid ROS 2 package).

- If it's a Python package, it should have setup.py and setup.cfg.

---

## Simulation Setup

### 1. Launch Gazebo Simulation

To launch the Gazebo world and load the robot model:


    ros2 launch arm_robot launch_sim.launch.py



### 2. Control the Robot Arm Joints in Gazebo
Command the joint angles by launching the control file with desired angles (in degrees):

    ros2 launch arm_robot control.launch.py ax1:=45 ax2:=45 ax3:=45

Where:
   ax1 → Angle for R_J1
   
   ax2 → Angle for R_J4
   
   ax3 → Angle for R_J5

### 3. Visualize in RViz & Control with Joint State Publisher GUI

Adjust the joint sliders for:

    ros2 launch arm_robot rviz.launch.py
    
  - R_J1 (Shoulder)
  
  - R_J4 (Elbow)
  
  - R_J5 (Wrist)

---

## Joint Control Details
  - Joint Name	Description	Controlled By
  
  - R_J1	Shoulder Joint	Position Controller
  
  - R_J4	Elbow Joint	Position Controller
  
  - R_J5	Wrist Joint	Position Controller

---

## License
  - This project is licensed under the MIT License.
