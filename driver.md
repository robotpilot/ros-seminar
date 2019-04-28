# Driver for ROS

## RealSense D415 and D435
- http://wiki.ros.org/librealsense2
- http://wiki.ros.org/realsense2_camera

### Install Intel® RealSense™ SDK 2.0
- https://github.com/IntelRealSense/librealsense/blob/master/doc/distribution_linux.md
```bash
$ sudo apt-key adv --keyserver keys.gnupg.net --recv-key C8B3A55A6F3EFCDE || sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-key C8B3A55A6F3EFCDE
$ sudo add-apt-repository "deb http://realsense-hw-public.s3.amazonaws.com/Debian/apt-repo xenial main" -u
$ sudo apt install librealsense2-dkms librealsense2-utils librealsense2-dev
```
- Test using realsense-viewer
```bash
$ realsense-viewer
```
- Install ROS packages for RealSense 2
```bash
$ cd ~/catkin_ws/src/
$ git clone https://github.com/intel-ros/realsense.git
$ cd realsense
$ git checkout -b 2.2.3
$ cm
```

### Run Intel® RealSense™ D415 or D435
```bash
$ roslaunch realsense2_camera rs_camera.launch filters:=pointcloud
```
```bash
$ rviz
```
- 디스플레이 추가
  - Displays > Add > PointCloud2
- 디스플레이 옵션 설정
  - Displays > Global Options > Fixed frame = camera_link
  - Displays > PointCloud2 > Topic = /camera/depth/color/points


