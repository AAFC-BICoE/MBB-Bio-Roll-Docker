
FROM ubuntu:14.10

RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install -y --force-yes python-wxgtk2.8
RUN apt-get install -y --force-yes grass grass-core  grass-dev grass-dev-doc grass-doc grass-gui

# From: http://fabiorehm.com/blog/2014/09/11/running-gui-apps-with-docker/
RUN export uid=1000 gid=1000 && \
    mkdir -p /home/developer && \
    echo "developer:x:${uid}:${gid}:Developer,,,:/home/developer:/bin/bash" >> /etc/passwd && \
    echo "developer:x:${uid}:" >> /etc/group && \
    echo "developer ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/developer && \
    chmod 0440 /etc/sudoers.d/developer && \
    chown ${uid}:${gid} -R /home/developer



USER developer
ENV HOME /home/developer
CMD /usr/bin/grass

# To run:
#  $ docker run -ti --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix IMAGE_HASH
#
