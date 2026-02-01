# kubernetes
# Project for learning kubernetes


# Kubernetes – Stateless Application Example

## Description
Project contains an example of stateless application that is run in Kubernetes with the help of the following commands: 

- Namespace
- Deployment (3 replicas)
- Resource requests / limits
- Readiness i Liveness Probes
- Service
- Job and CronJob
---

## Requirements
- Kubernetes cluster (minikube / kind / k3s)
- kubectl configured for the cluster

---

## How to run application

1. Create namespace:
```bash
kubectl apply -f namespace.yaml
```

2. Run application
```
kubectl apply -f deployment.yaml
kubectl apply -f cluster-ip.yaml
kubectl apply -f job.yaml
kubectl apply -f cronjob.yaml
```
3. Check resources
```
kubectl get all -n dev
```
4. Check replicas
```
kubectl get pods -n dev
```
5. Check resource requests / limits
```
kubectl describe pod <pod-name> -n dev
```
6. Check readnessProbe
```
kubectl get pods -n dev
kubectl describe pod <pod-name> -n dev
```
7. Check livenessProbe
```
kubectl get pods -n dev
kubectl describe pod <pod-name> -n dev
```
8. Check rollingUpdate
   1. change image version
```
kubectl set image deployment/nginx-deployment nginx=nginx:1.26 -n dev
```
9. Observe rollout and pods:
```
kubectl rollout status deployment nginx-deployment -n dev
kubectl get pods -n dev -w
```


