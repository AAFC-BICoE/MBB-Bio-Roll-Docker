
After building:
To run:
$ docker run -ti --rm -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix IMAGE_HASH

Will display X properly. 

Borrowed from: http://fabiorehm.com/blog/2014/09/11/running-gui-apps-with-docker/