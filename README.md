# learning-k8s (docker, k8s, etc.)

### build docker file:
  	
  	$ docker build -t hello-world:0.0.1 docker/.


### create a pod:
	
	$ kubectl apply -f hello_world.yaml
	
### create a replication controller:

	$ kubectl apply -f rc.yaml
	
### expose the replication controller to a service:

	$ kubectl expose rc hello-rc --name=hello-svc --target-port=8080 --type=NodePort


### create a service with manifest file:

	$ kubectl apply -f svc.yaml

### check the description of service:

	$ kubectl describe service hello-svc

### check the endpoints to get the description of all the pods:
	
	$ kubectl describe ep hello-svc

### create a deployment:

	$ kubectl apply -f deployment.yaml

### make a update/rollback:
	 
#### Update the deploy.yaml file with new/old images and run the same command with the yaml file with --record, example:

	  $ kubectl apply -f deploy.yaml --record

### check the deployment status:

	$ kubectl rollout status deployment hello-deploy

### check the multiple replication controller status:

	$ kubectl get rs    

### rollback to a previous deployment state:

#### check the history of deployments:
	
	$ kubectl rollout history deployment hello-deploy

#### revert to one particular version

	$ kubectl rollout undo deployment hello-deploy --to-revision = <revision no.>

## To install and run services on a remote k8s cluster, use helm. 

#### if you're using helm 2 or below, use tiller at remote to receive the helm instructions from client.
