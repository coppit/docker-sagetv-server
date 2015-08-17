docker-sagetv-server
--------------------

This is a Docker container for running the [SageTV Media Center](http://sage.tv/) server. SageTV is a digital video
recording (DVR) and home theater PC (HTPC) package, with clients for OS X, Windows, and Linux. Currently only
network-based tuners like the [SiliconDust HDHomerun](https://www.silicondust.com/) products are supported.

**THIS IS A WORK IN PROGRESS**

See [this thread](https://goo.gl/0wdnY0) for details.

Usage
=====

This docker image is available as a [trusted build on the docker index](https://hub.docker.com/r/coppit/sagetv-server/).

Run:

`sudo docker run -d --name sagetv-server -v /host/path:/var/media/pictures -v /host/path:/var/media/music -v /host/path:/var/media/videos -v /host/path:/var/recordings --net=host -t coppit/sagetv-server`

We need to run the container with host networking in order for the server to allow clients to connect from the local
network. (Otherwise the private container network causes the server to treat every client as a remote client.)

To check the status, run:

`docker logs sagetv-server`
