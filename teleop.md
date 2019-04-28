# Joystick (DS3 / DS4 / XBOX)

## Install joystick driver, joystick configuration tool, ROS joystick package
- 조이스틱 관련 패키지 설치 (바이너리 설치, 삭제, 소스코드 설치 등)
```bash
$ sudo apt install joystick jstest-gtk ros-kinetic-joy
$ sudo apt purge ros-kinetic-teleop-twist-joy
$ cd ~/catkin_ws/src
$ git clone https://github.com/robotpilot/teleop_twist_joy.git
$ cd ~/catkin_ws && catkin_make
```

## Set joystick(Dual Shock 3,4) controller
1. 블루투스 관리 툴(예: blueberry 또는 blueman)을 실행한다.
1. DS3,4의 PS(버튼10번) 버튼을 누른다: 페어링 모드 진입
1. USB로 DS3,4와 PC를 유선으로 연결한다.
1. 블루투스 관리 툴(예: blueberry 또는 blueman)에서 페어링 허가 여부를 물으면 허락한다.
1. USB 연결을 제거 후, DS3,4의 PS(버튼10번) 버튼을 누르고 블루투스 관리 툴에서 DS3,4를 찾아 블루투스로 연결한다.
1. 하기의 joystick configuration tool로 키를 확인하고, Calibration 기능을 통해 모든 축과 버튼을 셋팅한다.
```bash
$ jstest-gtk 
```

## Check joystick key map
- [ds3.config.yaml](https://github.com/robotpilot/teleop_twist_joy/blob/melodic-devel/config/ds3.config.yaml)
- [ds4.config.yaml](https://github.com/robotpilot/teleop_twist_joy/blob/melodic-devel/config/ds4.config.yaml)

## Run teleop node (DS3,4)
- joystick device -> joy_node (joy, sensor_msgs/Joy) -> teleop_twist_joy (cmd_vel, geometry_msgs/Twist)
```bash
$ roslaunch teleop_twist_joy teleop.launch joy_config:=ds3
or
$ roslaunch teleop_twist_joy teleop.launch joy_config:=ds4
```

## Test teleop node (DS3,4) with turtlesim_node
```bash
$ rosrun turtlesim turtlesim_node
$ roslaunch teleop_twist_joy teop.launch joy_config:=ds3 __ns:=turtle1
or
$ roslaunch teleop_twist_joy teop.launch joy_config:=ds4 __ns:=turtle1
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
