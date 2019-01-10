# Continuous Delivery for Helm Charts on Kubernetes Engine using Concourse

All steps are here:
https://cloud.google.com/solutions/continuous-integration-helm-concourse

## 1. Create a GKE cluster to deploy Concourse and the sample Helm chart with the following command:
```
gcloud container clusters create concourse --image-type ubuntu \
    --machine-type n1-standard-2 --zone europe-west4-a \
    --scopes cloud-source-repos-ro,storage-full
```
for windows:
```
gcloud container clusters create concourse --image-type ubuntu^
    --machine-type n1-standard-2 --zone europe-west4-a^
    --scopes cloud-source-repos-ro,storage-full
```
