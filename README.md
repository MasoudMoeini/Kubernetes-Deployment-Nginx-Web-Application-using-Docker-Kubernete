# Kubernetes Deployment Web Application using Docker-Desktop Kubernetes
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
Create a Service for web-app-deployment(type: ClusterIP,or NodePort) 
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
curl <spec: ClusterIP e.g 10.98.125.249>:<port e.g 8080>
```
```
curl http://localhost:<nodePort-Port e.g 31726>
```
Create a Service for web-app-deployment(type: LoadBalancer) 
```
kubectl apply -f ./web-app-svc-lb.yaml
```
# Create Ingeress:
make sure ingress-nginx-controller already installed: [Instruction](https://techdocs.broadcom.com/us/en/ca-enterprise-software/it-operations-management/dx-platform-on-premise/1-0/installing/reference-information/Verify-if-the-NGINX-Ingress-Controller-is-Running.html) 
```
kubectl get all --all-namespaces
```
if not: [Instruction](https://docs.nginx.com/nginx-ingress-controller/installation/installation-with-helm/)
```
kubectl apply -f minimal-ingress.yaml
```
```
kubectl get ingress
```
Updating /etc/hosts file with "192.168.64.4 web-app-host.info" On macOs [Instruction](https://help.nexcess.net/en_US/miscellaneous/how-to-find-the-hosts-file-on-my-mac)
```
curl web-app-host.info
```
Delete all  Resources:
```
kubectl delete all --all --all-namespaces
```


