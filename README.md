# ROS 2 first package

My first ROS 2 package, written while learning ROS 2 (Jazzy) with the Articulated Robotics series. It has two launch files that start the `demo_nodes_cpp` talker and listener, which publish and subscribe to the `chatter` topic.

## Build and run

Clone it into the `src` folder of a colcon workspace (the package is called `my_package`):

```bash
cd ~/ros2_ws/src
git clone https://github.com/jaswin-codes/ros2-first-package.git my_package
cd ~/ros2_ws
colcon build --packages-select my_package
source install/setup.bash
```

Then, in two terminals:

```bash
ros2 launch my_package talker.launch.py
ros2 launch my_package listener.launch.py
```

You should see the listener print each message the talker publishes. `ros2 topic echo /chatter` shows the same messages.

## Files

| File | What it does |
|------|--------------|
| `launch/talker.launch.py` | Starts the `demo_nodes_cpp` talker node |
| `launch/listener.launch.py` | Starts the `demo_nodes_cpp` listener node |
| `package.xml`, `CMakeLists.txt` | ament_cmake package definition; installs the launch files |

## Next

This is the starting point for a ROS 2 mobile-robot project (simulation in Gazebo, then SLAM and Nav2).
