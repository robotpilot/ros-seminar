# [사전 준비 사항]
- 무선 인터넷 연결이 가능하고 프로그래밍이 작업을 위한 개인 컴퓨터 준비
- 컴퓨터의 그래픽 카드 및 CPU 성능에 따라 시뮬레이터 Gazebo가 원할히 작동하지 않을 수도 있음
- 개인 컴퓨터에 아래의 운영체제 및 소프트웨어 설치가 요구됨
 
1. PC 사양
    - 사용하는 목적에 따라 다르겠지만 아래 스펙 정도면 될듯 싶습니다.
    - 하기 권장 사양은 3D 시뮬레이터등이 원할히 동작하는 수준이며 이 사양에 못 미쳐도 교육 진행에는 문제 없습니다.
    - Processor: Intel Core i5 or i7 CPU / 2 GHz Dual Core Processor or better
    - RAM: 4GB 
    - Storage: 100GB of free hard drive space
    - Graphics Card: NVIDIA GeForce GTX 9xx (for Gaezebo 3D Simulator)
    - WiFi, USB

1. Ubuntu 16.04.x LTS 64bit 설치
   - http://releases.ubuntu.com/16.04/ubuntu-16.04.6-desktop-amd64.iso (ISO 파일 받으실 때, 무료) 
   - http://www.ubuntu.com/download/desktop/create-a-usb-stick-on-windows (bootable USB를 만들 때, 무료)
   - Ubuntu 를 설치하실 때, 표시 언어는 한국어가 아닌 영문으로 설정해주세요. 한국어로 설치해도 사용상의 문제는 없지만 에러가 났을 경우 에러가 한국어로 나와서 관련 답변들이 잘 검색되지 않습니다.
   - Ubuntu 를 설치하실 때, 어려움을 겪으시는 분들이 많으신데 '윈도우즈, 우분투, 멀티부팅'  등의 키워드를 검색하시면 다양한 솔루션이 나오니 참고 하시면 될 듯 싶습니다.
   - VirtualBox를 이용한 Linux 및 ROS 설치도 가능하지만 일부 교육 과정(시뮬레이션)은 진행할 수 없음을 참고해주세요.
   - Ubuntu가 아닌 Linuxe Mint도 사용 가능합니다.
   - 윈도우즈와 멀티부팅 가능

1. Linux 사전 지식
    - 리눅스 설치는 가능해야하며 간단한 리눅스 명령어 정도는 숙지하면 좋습니다.

1. ROS Kinetic 설치
   - http://cafe.naver.com/openrt/14575

1. 강의에서 사용되는 패키지 및 의존성 패키지 설치
   - 위 1번과 2번의 운영체제 및 ROS 설치가 모두 완료되면 하기의 내용을 설치해주세요.
   - [의존성 소프트웨어 및 터틀봇3 관련 ROS 패키지 설치하기]
   - '6.1.3. Install Dependent ROS Packages' 만 진행할 것
   - http://emanual.robotis.com/docs/en/platform/turtlebot3/pc_setup/#install-dependent-ros-packages
   - [아두이노 IDE 설치하기] (임베디드 시스템과 ROS 연동을 하실분만 설치할 것)
   - '4.1.1. USB Port Settings' 부터 '4.1.5.2 Install the OpenCR package via Boards Manager' 까지만 진행할 것
   - http://emanual.robotis.com/docs/en/parts/controller/opencr10/#arduino-ide
   - [OpenManipulator 관련 설치하기]
   - '5.3. Install ROS Packages' 만 진행할 것
   - http://emanual.robotis.com/docs/en/platform/openmanipulator_x/ros_setup/#install-ubuntu-on-pc

1. 강의 자료 다운로드 하기 (모든 PDF 파일)
   - https://github.com/robotpilot/ros-seminar

1. 미리 설치해두면 좋은 수업관련 ROS 패키지
### For SLAM and Naviagtion using TurtleBot3 (chapter 10, 11)
```
$ sudo apt-get install ros-kinetic-joy ros-kinetic-teleop-twist-joy ros-kinetic-teleop-twist-keyboard ros-kinetic-laser-proc ros-kinetic-rgbd-launch ros-kinetic-depthimage-to-laserscan ros-kinetic-rosserial-arduino ros-kinetic-rosserial-python ros-kinetic-rosserial-server ros-kinetic-rosserial-client ros-kinetic-rosserial-msgs ros-kinetic-amcl ros-kinetic-map-server ros-kinetic-move-base ros-kinetic-urdf ros-kinetic-xacro ros-kinetic-compressed-image-transport ros-kinetic-rqt-image-view ros-kinetic-gmapping ros-kinetic-navigation ros-kinetic-interactive-markers
```
```
$ cd ~/catkin_ws/src/
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3.git
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git
$ git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws && catkin_make
```
### For Manipulation using OpenManipulator (chapter 13)
```
$ sudo apt-get install ros-kinetic-ros-controllers ros-kinetic-gazebo* ros-kinetic-moveit* ros-kinetic-industrial-core
```
```
$ cd ~/catkin_ws/src
$ git clone https://github.com/ROBOTIS-GIT/DynamixelSDK.git
$ git clone https://github.com/ROBOTIS-GIT/dynamixel-workbench.git
$ git clone https://github.com/ROBOTIS-GIT/dynamixel-workbench-msgs.git
$ git clone https://github.com/ROBOTIS-GIT/open_manipulator.git
$ git clone https://github.com/ROBOTIS-GIT/open_manipulator_msgs.git
$ git clone https://github.com/ROBOTIS-GIT/open_manipulator_simulations.git
$ git clone https://github.com/ROBOTIS-GIT/robotis_manipulator.git
$ cd ~/catkin_ws && catkin_make
```

* Ubuntu 설치 및 ROS 설치에 관련하여 질문 사항이 있으시면 pyo@robotis.com 로 연락주세요.
* Ubuntu 및 ROS는 교육 전 설치가 안되면 교육 진행에 불편함이 있으니 꼭 미리 설치해주시기 바랍니다.

# [기타]
## [임베디드 예제 코드]
- [turtlebot3_core.ino](https://github.com/ROBOTIS-GIT/OpenCR/blob/master/arduino/opencr_arduino/opencr/libraries/turtlebot3/examples/turtlebot3_burger/turtlebot3_core/turtlebot3_core.ino)
- [turtlebot3_sensor.cpp](https://github.com/ROBOTIS-GIT/OpenCR/blob/master/arduino/opencr_arduino/opencr/libraries/turtlebot3/src/turtlebot3/turtlebot3_sensor.cpp)
