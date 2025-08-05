# ros2-turtle
#  Manipulating Turtlesim in ROS2 (Humble)

This project demonstrates how to install and use the `turtlesim` package in ROS 2 Humble. It includes installation, running nodes, teleoperation, remapping, and exploring topics and services.

---

##  Used Tools & Environment

- **Operating System:** Ubuntu (inside VirtualBox)
- **ROS Version:** ROS 2 Humble Hawksbill
- **Main Package:** `turtlesim`
- **Other Tools:** Terminal, Firefox (for documentation), GitHub (for publishing)

---

##  Installation

Update your system and install `turtlesim`:

```bash
sudo apt update
sudo apt install ros-humble-turtlesim
```

Check executables:

```bash
ros2 pkg executables turtlesim
```

You should see:

```bash
turtlesim draw_square
turtlesim mimic
turtlesim turtle_teleop_key
turtlesim turtlesim_node
```

---

##  Running Turtlesim

### 1. Start the Turtlesim Node

```bash
ros2 run turtlesim turtlesim_node
```

![Turtlesim Window](https://github.com/Raghad-ALSalmi/ros2-turtle/blob/main/photo_5802963265070943054_y.jpg)

### 2. Control the Turtle Using Keyboard

```bash
ros2 run turtlesim turtle_teleop_key
```

Use the arrow keys to move the turtle.
- `G|B|V|C|D|E|R|T` to rotate to specific angles
- `F` to cancel rotation, `Q` to quit
##  Project Screenshots

![Teleop](https://github.com/Raghad-ALSalmi/ros2-turtle/blob/main/photo_5802963265070943052_y.jpg)

![Teleop](https://github.com/Raghad-ALSalmi/ros2-turtle/blob/main/photo_5802963265070943050_y.jpg)
![Teleop](https://github.com/Raghad-ALSalmi/ros2-turtle/blob/main/photo_5802963265070943048_y%20(1).jpg)
![Teleop](https://github.com/Raghad-ALSalmi/ros2-turtle/blob/main/photo_5802963265070943049_y.jpg)

---

##  Node Remapping

To rename your node:

```bash
ros2 run turtlesim turtlesim_node --ros-args --remap __node:=my_turtle
```

This allows launching multiple nodes with different names.

---

##  Testing Topics

### View list of active topics:

```bash
ros2 topic list
```

### Echo topic data:

```bash
ros2 topic echo /turtle1/pose
```

### Publish directly to a topic:

```bash
ros2 topic pub /turtle1/cmd_vel geometry_msgs/msg/Twist "{linear: {x: 2.0}, angular: {z: 1.8}}"
```

---

## Using draw_square

Turtle will draw a square path automatically:

```bash
ros2 run turtlesim draw_square
```

[![Watch the video](https://github.com/Raghad-ALSalmi/ros2-turtle/blob/main/IMG_5316.MOV)
[![Watch the video](https://github.com/Raghad-ALSalmi/ros2-turtle/blob/main/IMG_5314.MOV)

---

## 🧠 Extra Tips

- You can launch multiple turtles using different names.
- You can simulate communication using `talker` and `listener` nodes.
- If you're lost, always check the official [ROS2 Documentation](https://docs.ros.org/en/humble/index.html).

---
---





##  Project Goal

The purpose of this project is to demonstrate how to use the ROS2 `turtlesim` package to control and manipulate a simulated robot turtle. It helps you understand the basics of ROS 2 concepts such as:
- Nodes
- Topics
- Services
- Parameters
- Remapping

---

##  Quick Start Guide

Follow these steps to get everything up and running:

```bash
# 1. Update packages
sudo apt update

# 2. Install turtlesim
sudo apt install ros-humble-turtlesim

# 3. Run the turtlesim node
ros2 run turtlesim turtlesim_node

# 4. In another terminal, control it with keyboard
ros2 run turtlesim turtle_teleop_key
```

---

## 🛠 Common Errors & Fixes

| Error Message                                | Solution                                                                 |
|---------------------------------------------|--------------------------------------------------------------------------|
| `bash: syntax error near unexpected token`  | Don’t use `<` or `>` in the terminal. Replace with actual values.        |
| `DISPLAY not set` or GUI doesn’t appear     | Make sure you’re using a graphical interface, not just a terminal shell. |
| `command not found: ros2`                   | Source the setup script: `source /opt/ros/humble/setup.bash`             |
| Turtle not moving                           | Make sure `turtlesim_node` is running and not frozen.                    |

---

##  Useful Links

- [ROS2 Documentation](https://docs.ros.org/en/humble/index.html)
- [Turtlesim Tutorials](https://docs.ros.org/en/humble/Tutorials/Beginner-CLI-Tools/Introducing-Turtlesim/Introducing-Turtlesim.html)
- [ROS2 Commands Cheat Sheet](https://github.com/ros2/ros2_documentation/blob/rolling/source/Tutorials/Beginner-CLI-Tools/Introducing-Turtlesim.rst)

---

## 💡 Future Improvements

Here are some ideas to build on top of this project:

- 🔁 Launch multiple turtles and control them with different remapped topics.
- 🧠 Add AI or logic to automatically move turtles in shapes (square, triangle).
- 📷 Record the movements using rosbag2 and replay them.
- 🧪 Add unit tests using launch test tools.
- 🌐 Create a web interface to control the turtle using ROS Bridge.

---
