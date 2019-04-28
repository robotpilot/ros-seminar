# Joystick (DS3 / DS4 / XBOX)

## Install joystick driver, joystick configuration tool, ROS joystick package
- 조이스틱 관련 패키지 설치 (바이너리 설치, 삭제, 소스코드 설치 등)
```bash
$ sudo apt install joystick jstest-gtk ros-kinetic-joy
$ sudo apt purge ros-kinetic-teleop-twist-joy
$ cd ~/catkin_ws/src
$ git clone https://github.com/ros-teleop/teleop_twist_joy.git
$ cd ~/catkin_ws && catkin_make
```

## Modify joystick mapping
- `~/catkin_ws/src/teleop_twist_joy/config/ps3.config.yaml`
```yaml
enable_button: 5  # R1 button
enable_turbo_button: 4  # L1 button

axis_linear: 1
scale_linear: 0.7
scale_linear_turbo: 1.5

axis_angular: 3
scale_angular: 0.4
scale_angular_turbo: 1.0
```

## Set oystick(Dual Shock 3) controller
1. 블루투스 관리 툴(예: blueberry 또는 blueman)을 실행한다.
1. DS3의 PS(버튼10번) 버튼을 누른다: 페어링 모드 진입
1. USB로 DS3와 PC를 유선으로 연결한다.
1. 블루투스 관리 툴(예: blueberry 또는 blueman)에서 페어링 허가 여부를 물으면 허락한다.
1. USB 연결을 제거 후, DS3의 PS(버튼10번) 버튼을 누르고 블루투스 관리 툴에서 DS3를 찾아 블루투스로 연결한다.
1. 하기의 joystick configuration tool로 키를 확인한다.
```bash
$ jstest-gtk 
```

## Run teleop node
- joystick device -> joy_node (joy, sensor_msgs/Joy) -> teleop_twist_joy (cmd_vel, geometry_msgs/Twist)
```bash
$ roslaunch teleop_twist_joy teleop.launch
```

# 참고 사항
## 원격 제어를 위한 정보
- http://wiki.ros.org/joy
- http://wiki.ros.org/teleop_tools
- http://wiki.ros.org/key_teleop
- http://wiki.ros.org/joy_teleop
- http://wiki.ros.org/teleop_twist_joy
- http://wiki.ros.org/teleop_twist_keyboard
- http://wiki.ros.org/turtlebot_teleop
- http://wiki.ros.org/turtlebot3_teleop

## 원격 제어를 위한 키보드 관련 소스 코드
- [teleop_turtle_key.cpp](https://github.com/ros/ros_tutorials/blob/melodic-devel/turtlesim/tutorials/teleop_turtle_key.cpp)
- [turtlebot_teleop_key](https://github.com/turtlebot/turtlebot/blob/kinetic/turtlebot_teleop/scripts/turtlebot_teleop_key)
- [turtlebot3_teleop_key](https://github.com/ROBOTIS-GIT/turtlebot3/blob/master/turtlebot3_teleop/nodes/turtlebot3_teleop_key)
- [key_teleop.py](https://github.com/ros-teleop/teleop_tools/blob/kinetic-devel/key_teleop/scripts/key_teleop.py)
- [teleop_twist_keyboard.py](https://github.com/ros-teleop/teleop_twist_keyboard/blob/master/teleop_twist_keyboard.py)
