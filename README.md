## Setup

```shell
rosdep install -i --from-path src --rosdistro jazzy -y
colcon build
# colcon build --packages-select learning_tf2_py
source install/setup.bash
```

## Usage

### Static Broadcaster

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

### Broadcaster

```shell
ros2 launch learning_tf2_py turtle_tf2_demo_launch.py
ros2 run turtlesim turtle_teleop_key
ros2 run tf2_ros tf2_echo world turtle1
```

### Fixed Frame Broadcaster (carrot)

```shell
ros2 launch learning_tf2_py turtle_tf2_fixed_frame_demo_launch.py target_frame:=carrot1
```

### Dynamic Frame Broadcaster (carrot)

```shell
ros2 launch learning_tf2_py turtle_tf2_dynamic_frame_demo_launch.py
```

### Unit tests

```shell
colcon test
# or
colcon test --event-handlers console_cohesion+

colcon test-result --all # echo $? shows 0 for success and 1 for failure
```

## Extra

TF visualisation:

```shell
ros2 run tf2_tools view_frames
```