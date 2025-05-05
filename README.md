## Setup

```shell
rosdep install -i --from-path src --rosdistro jazzy -y
colcon build
# colcon build --packages-select learning_tf2_py
source install/setup.bash
```

## Usage

```shell
ros2 run learning_tf2_py static_turtle_tf2_broadcaster mystaticturtle 0 0 1 0 0 0
ros2 run tf2_ros static_transform_publisher --x x --y y --z z --yaw yaw --pitch pitch --roll roll \
  --frame-id frame_id --child-frame-id child_frame_id
ros2 run tf2_ros static_transform_publisher --x x --y y --z z --qx qx --qy qy --qz qz --qw qw --frame-id frame_id --child-frame-id child_frame_id  
```

Launch file:

```shell
ros2 launch learning_tf2_py example_launch.py
```