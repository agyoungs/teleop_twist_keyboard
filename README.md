# teleop_twist_keyboard
Generic Keyboard Teleoperation for ROS

## Launch

To run: `ros2 run teleop_twist_keyboard teleop_twist_keyboard`

## Usage

```
This node takes keypresses from the keyboard and publishes them as Twist
messages. It works best with a US keyboard layout.
---------------------------
Moving around:
   u    i    o
   j    k    l
   m    ,    .

For Holonomic mode (strafing), hold down the shift key:
---------------------------
   U    I    O
   J    K    L
   M    <    >

t : up (+z)
b : down (-z)

anything else : stop

q/z : increase/decrease max speeds by 10%
w/x : increase/decrease only linear speed by 10%
e/c : increase/decrease only angular speed by 10%

CTRL-C to quit
```

# Twist with header
Publishing a `TwistStamped` message instead of `Twist` can be enabled with the `stamped` parameter. Additionally the `frame_id` of the `TwistStamped` message can be set with the `frame_id` parameter.
```
ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -r -p stamped:=True -p frame_id:="base_link"
