ARG ROS_DISTRO=kinetic
FROM ros:${ROS_DISTRO}-ros-core
ARG ROS_DISTRO

LABEL maintainer="Yuxiang Gao ygao73@jhu.edu.com"

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && \
    apt-get install -qqy \
    tmux \
    wget \
    git \
    vim \
    chrony \
    python-rosinstall \
    python-catkin-tools && \
    apt-get upgrade -y && \
    apt-get autoremove && \
    rm -rf /var/lib/apt/lists/

COPY ./ros_entrypoint.sh /
ENTRYPOINT ["/ros_entrypoint.sh"]

CMD ["roscore"]
