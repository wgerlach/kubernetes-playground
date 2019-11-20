# kubernetes-playground



install helm:
```bash
brew install kubernetes-helm
helm repo add stable https://kubernetes-charts.storage.googleapis.com/
helm repo update

```




```bash

kubectl config use-context minikube
minikube addons disable ingress


helm install  ingress stable/nginx-ingress --set controller.hostNetwork=true,controller.kind=DaemonSet

kubectl get svc ingress-nginx-ingress-controller -o jsonpath="{.status.loadBalancer.ingress[0].ip}"







#Volume
kubectl create -f ./localVolume.yaml 

kubectl get persistentvolume/pv0001
kubectl get pv
kubectl describe pv pv0001


kubectl apply -f pv-claim.yaml

kubectl get pvc

kubectl create -f pod.yaml



# ingress controller


kubctl create -f mgrast-web-v4-deployment.yaml



kubectl get services

kubectl expose deployment mgrast-web-v4-deployment --target-port=80 --type=NodePort


minikube service mgrast-web-v4-deployment --url
minikube service ingress-nginx --url



#access VM
screen ~/Library/Containers/com.docker.docker/Data/vms/0/tty 


```