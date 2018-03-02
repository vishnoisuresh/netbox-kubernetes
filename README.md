# netbox-kubernetes
Kubernetes manifest resources for Netbox.  all images are pulled from docker hub. Netbox images pulled from https://hub.docker.com/r/ninech/netbox/

**this is not for production this is just for testing**


## Quickstart on GKE Google Container Engine (for testing)

To get NetBox up and running:

```
$ git clone 
$ cd netbox-kubernetes
$ gcloud container clusters get-credentials <clustername> --zone <zone> --project <project>
$ kubectl apply -f netbox-namespace.yaml 
$ kubectl apply -f configmap.yaml --namespace netbox
$ kubectl apply -f postgres.yaml --namespace netbox
$ kubectl apply -f deployment.yaml --namespace netbox
$ kubectl apply -f service.yaml --namespace netbox
$ kubectl apply -f ingress.yaml --namespace netbox
```

At the moment you can access the application using follwing command. 
```
$ kubectl get pods -n netbox
```
Now you can check what is your external ip
```
$ kubectl -n netbox get svc
```
The application will be available after a few minutes.
"http://<externalIP>"

```

Default credentials:

* Username: **netbox**
* Password: **password**

```

## Dependencies
https://hub.docker.com/r/ninech/netbox/

## Configuration

You can configure the app using environment variables. These are defined in ConfigMap section in `configmap.yaml` file.

## RoadMap
Helm Chart

## About
This is a living document. If you spot areas that can be improved or rewritten, contributions are welcome! 
