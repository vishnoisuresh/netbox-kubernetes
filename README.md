# netbox-kubernetes
Kubernetes manifest resources for Netbox.  all images are pulled from docker hub. Netbox images pulled from https://hub.docker.com/r/ninech/netbox/


## Quickstart on Minikube

To get NetBox up and running:

```
$ git clone -b master https://github.com/vishnoisuresh/netbox-kubernetes.git
$ cd netbox-kubernetes
$ kubectl apply -f netbox-namespace.yaml 
$ kubectl apply -f postgres-all.yaml --namespace netbox
$ kubectl apply -f netbox-all.yaml --namespace netbox
$ kubectl apply -f nginx-all.yaml --namespace netbox
```

At the moment you can access the application using follwing command. 
```
$ kubectl get pods -n netbox
```
Now you can replace  Nginx-Pod-Name
```
$ kubectl port-forward Nginx-Pod-Name 8001:80 --namespace netbox
```
**8001 is a localport** It can be changed according to you. 
The application will be available after a few minutes.
"http://localhost:8001"

Default credentials:

* Username: **admin**
* Password: **admin**


## Dependencies
https://hub.docker.com/r/ninech/netbox/

## Configuration

You can configure the app using environment variables. These are defined in ConfigMap section in `netbox-all.yaml` file.

## RoadMap
Ingress-Contorler 
Helm Chart

## About
This is a living document. If you spot areas that can be improved or rewritten, contributions are welcome! 
