# Kubernetes Deployment Nginx Web Application using Docker-Kubernetes
Clone Repo and Enable Kubernetes Cluster on Docker Desctop. <br>
RUN following command to create deployment and Service in Kubernetes cluster. <br>
```
kubectl apply -f ./nginx-deployment.yaml
```
```
kubectl get pods
```
Scaling a Deployment:
```
kubectl scale deployment/nginx-deployment --replicas=10
kubectl autoscale deployment/nginx-deployment --min=10 --max=15 --cpu-percent=80
```
Create a Service for nginx-deployment(type: NodePort) 
```
kubectl apply -f ./nginx-svc.yaml
```
```
kubectl get all 
```
```
kubectl get service nginx-deployment
```
Access to the service via Url
```
curl http://localhost:<nodePort-Port e.g 31726>
```

