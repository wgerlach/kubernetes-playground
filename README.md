# kubernetes-playground

```
brew install minikube
```

## install helm:
```bash
brew install kubernetes-helm
helm repo add stable https://kubernetes-charts.storage.googleapis.com/
helm repo update

```



## fix context
```bash
kubectl api-resources

kubectl config get-contexts 
kubectl config use-context bio-worker
kubectl config use-context minikube

```

## ingress controller

```bash
kubectl get svc

helm list
helm install traefik-ingress stable/traefik  --values traefik_values.yaml 
helm delete traefik-ingress
// https://github.com/helm/charts/tree/master/stable/traefik


kubectl describe svc traefik-ingress 
```

## 
```bash
kubectl get ingress
kubectl create -f ./ingress.yaml 

```

## create volume
```bash
kubectl get pv

kubectl create -f ./localVolume.yaml 

kubectl get persistentvolume/pv0001

kubectl describe pv pv0001

```


##  claim volume

```bash
kubectl apply -f pv-claim.yaml

kubectl get pvc

```

## create deployment

```bash


kubectl get deployment
kubectl delete deployment mgrast-web-v4-deployment
kubectl create -f mgrast-web-v4-deployment.yaml
kubectl describe deployment mgrast-web-v4-deployment

```

## create service

```bash
kubectl get services
kubectl delete service mgrast-web-v4-service
kubectl expose deployment mgrast-web-v4-deployment --port=80 --target-port=80 --name=mgrast-web-v4-service
kubectl describe service mgrast-web-v4-service


```

```bash

minikube service mgrast-web-v4-deployment --url
minikube service traefik-ingress  --url


```

```bash
#access VM
screen ~/Library/Containers/com.docker.docker/Data/vms/0/tty 


```