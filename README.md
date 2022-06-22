# Kubernetes Deployment Web Application using Docker-Kubernetes
Clone Repo and Enable Kubernetes Cluster on Docker Desctop. <br>
RUN following command to create deployment and Service in Kubernetes cluster. <br>
```
kubectl apply -f ./web-app-deployment.yaml
```
```
kubectl get pods -o wide
```
Scaling a Deployment:
```
kubectl scale deployment/web-app-deployment --replicas=10
kubectl autoscale deployment/web-app-deployment --min=10 --max=15 --cpu-percent=80
```
Create a Service for web-app-deployment(type: NodePort) 
```
kubectl apply -f ./web-app-svc.yaml
```
```
kubectl get all 
```
```
kubectl get service web-app-deployment
```
Access to the service via Url
```
curl http://localhost:<nodePort-Port e.g 31726>
```
# Create Ingeress:
```
kubectl apply -f minimal-ingress.yaml
```
```
kubectl get ingress
```
Updating /etc/hosts file with "192.168.64.4 web-app-host.info" On macOs [Introduction](https://help.nexcess.net/en_US/miscellaneous/how-to-find-the-hosts-file-on-my-mac)
```
curl hello-world.info
```
```
curl web-app-host.info
```
Delete all  Resources:
```
kubectl delete all --all --all-namespaces
```


