
# Workshop helm

https://inuits.eu/blog/an-introduction-to-helm/
https://kubernetes.io/docs/tutorials/hello-minikube/

## Installation 

- [Mac](Mac.md)
- [Ubuntu](Ubuntu.md)

## Running

We're going to use an ingress and metrics later on.
Let's first enable them otherwise we'll need a minikube restart

```bash
minikube addons enable ingress
minikube addons enable metrics-server
```

Start up and get the ip
```bash
minikube start
minikube ip
```

## Helming 

Adding the stable repo (it's the default repo you should use)
```bash
helm repo add stable https://kubernetes-charts.storage.googleapis.com
helm repo update
```

Installing something... Like prometheus
```bash
helm install prometheus stable/prometheus-operator
helm get values prometheus
```

## Ingress

Lets make sure we can access grafana.
The helm chart requires us to give a host name.
But for that we would need to add some dns resolution to our `/etc/hosts` file
We've prepared an ingress that routes everything to the grafana service

```bash
kubectl apply -f ing.yml
```

Now you should be able to do the following curl command:

```bash
curl http://"$(minikube ip)"
```

Or if you pick up the minikube ip then you should be able to visit in your browser

```bash
minikube ip
```

Default credentials:  admin / prom-operator 

## Cleaning up

```bash
minikube stop
minikube delete
```