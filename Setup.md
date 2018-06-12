Setup
========


Docker
------

First build the docker container in the `docker_apache` folder.

`docker build -t vertoforce/apache .`



Kubernetes
-------

Next make sure kubenetes server is online.

`minikube start`


Run the deployment

`kubectl run test --image=vertoforce/apache --port=5001`

Optionally scale the deployment to 5 instances

`kubectl scale --replicas=5 deploy test`

Set up / expose the service

`kubectl expose deployment test --type=NodePort --name=test-service`


Viewing Setup
------

Everything should now be set up, you can view the deployment using:

`kubectl get deployments`

You can see the pods using

`kubectl get pods`


Connecting and testing
----------------

First check the ip of the kubernetes ip

`minikube ip`

Then find the port the service is exposed on using

`kubectl get service`

Locate the 31005 like in this example:

`test-service   NodePort    10.99.227.136   <none>        5001:31005/TCP   7m`

Then connect to the service using the minikube_ip:port


