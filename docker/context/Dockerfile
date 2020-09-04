ARG ROS_DISTRO
FROM ros:${ROS_DISTRO}

RUN apt-get update && apt-get install -y \
  python3-pip \
#  ros-${ROS_DISTRO}-orocos-kdl \
#  ros-${ROS_DISTRO}-tf2-bullet \
#  ros-${ROS_DISTRO}-angles \
  && rm -rf /var/lib/apt/lists/*

#RUN pip3 install -U wheel pybullet pathlib numpy rosdep rosinstall-generator wstool rosinstall ros-buildfarm rosdistro rospkg pyyaml catkin_pkg catkin_tools
RUN pip3 install -U pybullet pathlib numpy

SHELL ["/bin/bash", "-c"]

RUN cd /root/ && git clone https://github.com/cram2/pycram.git
RUN cd /root/pycram/resources && git clone https://github.com/PR2/pr2_common.git
RUN cd /root/pycram/resources && git clone https://github.com/code-iai/iai_maps.git

#WORKDIR /root/ros_ws/
#RUN source /opt/ros/${ROS_DISTRO}/setup.bash \
#  && cd /root/ros_ws/ \
#  && catkin build

#RUN cd /root/ros_ws/src/pycram/pycram && pip3 install -e .