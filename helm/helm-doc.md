# Helm on GKE cluster

## 1. Create service account for helm
```
kubectl apply -f helm/helm-service-account.yaml
```

## 2. Initialise helm
```
helm init --service-account helm
```
