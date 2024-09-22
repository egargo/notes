# Kubernetes Notes


## Contents

- Installation
- Basics


## Basics

### minikube

```bash
# Start minikube
minikube start

# Start minikube with custom CPU and RAM resources
minikube start --cpus 4 --memory 4096

# Stop minikube
minikube stop

# Delete minikube
minikube delete
minikube delete --all

# Get minikube IP
minikube ip

# Open minikube dashboard
minikube dashboard --url
```

### kubectl

```bash
# Apply configuration
kubectl apply -f file.yml

# ConfigMaps
kubectl get configmaps
kubectl delete configmaps configmaps-name

# Deployment
kubectl get deployments.app
kubectl delete deployments.app deployment-name

# Service
kubectl describe svc secrvice-name
kubectl get svc
kubectl delete service service-name

# PV
kubectl get pv
kubectl delete pv pesistent-volume-name

# PVC
kubectl get pvc
kubectl delete pvc persistent-volume-claim-name

# Secrets
kubectl get secrets
kubectl delete secrets secrets-name

# Pods
kubectl get pods
```
