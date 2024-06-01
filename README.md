# Ultrasound-Setup

## Installation
- ROS control
  ```
  sudo apt-get install ros-humble-ros2-control
  ```
- UR packages
  ```
  sudo apt-get install ros-humble-ur-*
  ```
- Uninstall `ur-description` so you can use the customized version of the `xacro` provided by this repo.
  ```
  sudo apt-get purge ros-humble-ur-description
  ```
- Build F/T sensor drivers
  ```
  cd bota_ws
  colcon build --symlink-install
  ```
- Build ur workspace
  ```
  cd ur_ws
  colcon build --symlink-install
  ```
- Build controllers. Credits to [this](https://github.com/fzi-forschungszentrum-informatik/cartesian_controllers) repo.
  ```
  cd controller_ws
  colcon build --symlink-install
  ```

## Docker Image
1. A docker image can be pulled from [here](https://hub.docker.com/repository/docker/hydran00/ultrasound-setup/general) with
  ```
  docker pull hydran00/ultrasound-setup
  ```
2. Run the image with
  ```
  docker run -it --rm -d -e DISPLAY=$DISPLAY  -v /tmp/.X11-unix:/tmp/.X11-unix  ultrasound-setup
  ```
3. Attach a terminal with
  ```
  docker exec -t -i container_name /bin/bash
  ```