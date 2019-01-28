docker-ubuntu-vnc-desktop
=========================

[]([![Docker Pulls](https://img.shields.io/docker/pulls/ct2034/vnc-ros-kinetic-full.svg](https://hub.docker.com/r/ct2034/vnc-ros-kinetic-full/)
[]([![Docker Stars](https://img.shields.io/docker/stars/ct2034/vnc-ros-kinetic-full.svg](https://hub.docker.com/r/ct2034/vnc-ros-kinetic-full/)

Docker image to provide HTML5 VNC interface to access ROS kinetic on Ubuntu 16.04 with the LXDE desktop environment.  
This image is based on [ct2034/docker-ubuntu-vnc-desktop](https://github.com/ct2034/docker-ubuntu-vnc-desktop) and [fcwu/docker-ubuntu-vnc-desktop](https://github.com/fcwu/docker-ubuntu-vnc-desktop).

Quick Start
-------------------------

Run the docker image and open port `6085`

```
docker run -it --rm -p 6085:80 reizouko/ubuntu-vnc-ros-librealsense
```

Browse http://127.0.0.1:6085/

![screenshot](https://raw.github.com/KentaKawamata/docker-ubuntu-vnc-ros-librealsense/master/screenshots/realsense-docker.png)


Connect with VNC Viewer and protect by VNC Password
------------------

Forward VNC service port 5900 to host by

```
docker run -it --rm -p 6080:80 -p 5900:5900 reizouko/ubuntu-vnc-ros-librealsense
```

Now, open the vnc viewer and connect to port 5900. If you would like to protect vnc service by password, set environment variable `VNC_PASSWORD`, for example

```
docker run -it --rm -p 6085:80 -p 5900:5900 -e VNC_PASSWORD=mypassword reizouko/ubuntu-vnc-ros-librealsense
```

A prompt will ask password either in the browser or vnc viewer.


Troubleshooting and FAQ
==================

1. boot2docker connection issue, https://github.com/fcwu/docker-ubuntu-vnc-desktop/issues/2
2. Screen resolution is fitted to browser's window size when first connecting to the desktop. If you would like to change resolution, you have to re-create the container


License
==================

See the LICENSE file for details.
