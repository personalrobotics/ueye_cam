**Note to PersonalRobotics Users w/ ADA**

To use this node with ADA, do the following:

1. Make sure the ueye [USB driver](https://en.ids-imaging.com/download-ueye.html#4.61_Linux) is installed
2. Make sure that you can run `ueyecameramanager` and connect to the camera using the USB driver. Note that the camera requires a lot of bandwidth so it shouldn't be plugged into a hub.
3. Clone this repository into your catkin `src` directory.
4. `catkin_make` and source `devel/setup.bash`
5. Move `./resources/ueye_XS.yaml` camera calibration file into `~/.ros/camera_info/ueye_XS.yaml`
6. Launch `roslaunch ueye_cam xs_bayer_proc` to get a raw image stream through ROS
7. If you already have the *Structure Sensor* running, you can launch `depth_register.launch` instead, which will automatically run the `ueye_camera` and produce registered depth images and point clouds~

**DISCLAMER:**

This project was created within an academic research setting, and thus should
be considered as EXPERIMENTAL code. There may be bugs and deficiencies in the
code, so please adjust expectations accordingly. With that said, we are
intrinsically motivated to ensure its correctness (and often its performance).
Please use the corresponding web repository tool (e.g. github, bitbucket, etc)
to file bugs, suggestions, pull requests; we will do our best to address them
in a timely manner.


**LAYOUT:**
- ueye_cam/
  - cfg/:                 dynamic_reconfigure configuration files
  - include/:             header files
  - launch/:              roslaunch files
  - src/:                 source files
  - CMakeLists.txt:       CMake project configuration file
  - LICENSES:             license agreement
  - package.xml:          ROS/Catkin package file
  - nodelet_plugins.xml:  ROS nodelet specification file
  - README.md:            this file
- ~/.ros/camera_info/:    camera calibration yaml files
                          (see documentation for camera_calibration ROS package
                          for more details)
- ~/.ros/camera_conf/:    UEye camera parameter configuration files
                          (generatable using ueyedemo executable:
                          File -> save parameter -> to file...)


**DOCUMENTATION:**

www.ros.org/wiki/ueye_cam



Copyright (c) 2013, Anqi Xu

All rights reserved.

BSD3 license: see LICENSE file
