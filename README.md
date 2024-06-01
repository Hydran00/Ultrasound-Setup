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
