# Testing ASSIMP Ubuntu 18
FROM arm64v8/ros:eloquent
WORKDIR /home
# Add your customizations here
RUN apt update
RUN apt install git
RUN mkdir -p /home/ros_ws/src
RUN cd /home/ros_ws/src && git clone --recursive https://github.com/humanoid-path-planner/hpp-fcl.git
RUN cd /home/ros_ws
RUN apt install libboost-all-dev -y
RUN apt install liboctomap-dev -y
RUN apt install libassimp-dev -y
