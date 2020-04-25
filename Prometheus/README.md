## Steps to setup the prometheus container in your linux based docker.

	$ docker run -d --name prometheus --publish-all prom/prometheus:v2.3.1

## open a browser and go to [localhost:32768](http://0.0.0.0:32768/graph)



## To install prometheus on a k8s cluster:

#### install helm
		$ brew install helm

#### switch to the cluster 
		$ kubectl config use-context docker-desktop

#### add a helm repo
		$ helm repo add stable https://kubernetes-charts.storage.googleapis.com

#### install prometheus now 
###### make sure you have helm 3 or above
		
		
		$ helm install --generate-name stable/prometheus
