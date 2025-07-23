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

arm_robot/
├── launch/
│ ├── launch_sim.launch.py
│ ├── control.launch.py
│ └── rviz.launch.py
├── urdf/
│ └── robot_model.urdf.xacro
├── config/
│ └── controllers.yaml
├── rviz/
│ └── robot_config.rviz
├── scripts/
│ └── joint_controller.py
└── README.md


## Simulation Setup

### 1. Launch Gazebo Simulation

To launch the Gazebo world and load the robot model:

```bash
ros2 launch arm_robot launch_sim.launch.py


### 2. Control the Robot Arm Joints in Gazebo
Command the joint angles by launching the control file with desired angles (in degrees):

bash
Copy
Edit
ros2 launch arm_robot control.launch.py ax1:=45 ax2:=45 ax3:=45
Where:

ax1 → Angle for R_J1

ax2 → Angle for R_J4

ax3 → Angle for R_J5

### 3. Visualize in RViz & Control with Joint State Publisher GUI
bash
Copy
Edit
ros2 launch arm_robot rviz.launch.py
Adjust the joint sliders for:

R_J1 (Shoulder)

R_J4 (Elbow)

R_J5 (Wrist)

⚙️ Joint Control Details
Joint Name	Description	Controlled By
R_J1	Shoulder Joint	Position Controller
R_J4	Elbow Joint	Position Controller
R_J5	Wrist Joint	Position Controller

📦 Dependencies
ROS 2 (Humble or compatible version)

Gazebo (Fortress/Garden)

Joint State Publisher GUI

RViz2

ros2_control and gazebo_ros2_control

🛠️ To-Do
Add launch arguments for custom joint limits

Implement trajectory control

Add more joints for full arm motion

📜 License
This project is licensed under the MIT License.


