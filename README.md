# LEO IOT CORE

This is the root repository for the leo iot main application. It consists of multiple submodules which are the modules of the application and default files like the workflow, docker compose files, a basic gitignore and the git submodules file for the information about the submodules.

# Local K8s Deployment with kind

```
kind create cluster --config ./k8s-manifests/cluster-config.yaml
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/helm-chart-4.2.1/deploy/static/provider/kind/deploy.yaml
kubectl wait -n ingress-nginx --for=condition=ready pod --selector=app.kubernetes.io/component=controller --timeout=90s
```

```
kubectl apply -f ./k8s-manifests/database.yaml
kubectl apply -f ./k8s-manifests/backend.yaml
kubectl apply -f ./k8s-manifests/frontend.yaml
kubectl apply -f ./k8s-manifests/value-sim-database.yaml
kubectl apply -f ./k8s-manifests/value-sim.yaml
```
