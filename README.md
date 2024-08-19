# ros_ws

ROS2 Setup for Mac: https://docs.ros.org/en/jazzy/Installation/Alternatives/macOS-Development-Setup.html

* Note: When using a python venv, will need to run: pip install --upgrade setuptools

Python 3.12 has an issue with imp being deprecated ... for now just revert to 3.11


When building run:
```
colcon build --symlink-install --packages-skip-by-dep python_qt_binding --packages-skip python_orocos_kdl_vendor rviz_rendering rviz_rendering_tests
```


### Helpful links:
https://nu-msr.github.io/navigation_site/lectures/cmake_basics.html

# Building packages with cmake output
colcon build --symlink-install --event-handlers console_direct+ --cmake-args -DCMAKE_VERBOSE_MAKEFILE=ON


# For python_orocos
https://github.com/orocos/orocos_kinematics_dynamics/archive/refs/tags/v1.5.1.zip
```
  # This version must match orocos_kdl_vendor exactly
  fetchcontent_declare(
    python_orocos_kdl
    GIT_REPOSITORY https://github.com/orocos/orocos_kinematics_dynamics.git
    GIT_TAG db25b7e480e068df068232064f2443b8d52a83c7
    # PATCH_COMMAND
    #   ${CMAKE_COMMAND} -E chdir <SOURCE_DIR> git apply -p1 --ignore-space-change --whitespace=nowarn
    #     ${CMAKE_CURRENT_SOURCE_DIR}/patches/0001-fix-windows-debug.patch
  )
```
kdl_parser runs into issues with Eigen/Core in jacobian.hpp
** Also need to look into how to point the kdl headers from orocos_kdl_vendor to kdl_parser s

tf2_py fails as a result of not finding catkin_pkg which is installed via pip in anaconda

If rviz_rendering fails https://github.com/ros2/ros2/issues/1222


https://juraph.com/miscellaneous/ros2_and_gdb/

colcon build --symlink-install --packages-skip-by-dep python_qt_binding --packages-skip kdl_parser tf2_eigen_kdl tf2_py robot_state_publisher tf2_sensor_msgs tf2_geometry_msgs tf2_kdl tf2_ros_py tf2_tools examples_tf2_py dummy_robot_bringup interactive_markers test_tf2 geometry2 rviz_default_plugins rviz2

