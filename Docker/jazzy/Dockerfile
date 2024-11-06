# ROS2 Jazzy Dockerfile
FROM ros:jazzy

# install apt packages
RUN apt-get update && apt-get install -y \ 
    ros-${ROS_DISTRO}-demo-nodes-cpp \ 
    ros-${ROS_DISTRO}-demo-nodes-py && \
    rm -rf /var/lib/apt/lists/*
