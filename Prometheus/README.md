## Steps to setup the prometheus container in your linux based docker.

	$ docker run -d --name prometheus --publish-all prom/prometheus:v2.3.1

## open a browser and go to [0.0.0.0:32768](http://0.0.0.0:32768/graph)