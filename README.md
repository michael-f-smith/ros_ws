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
