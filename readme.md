# The google cloud kubernetes platform for micro-services

## 1. Deploy Concourse to kubernetes with helm

### 1.1. Instal Concourse with helm

```
helm install stable/concourse --name concourse
```

#### 1.2. Concourse can be accessed:

##### 1.2.1 Within your cluster, at the following DNS name at port 8080

```
concourse-web.default.svc.cluster.local
```

#### 1.2.2 From outside the cluster, run these commands in the same shell

```
export POD_NAME=$(kubectl get pods --namespace default -l "app=concourse-web" -o jsonpath="{.items[0].metadata.name}")
    echo "Visit http://127.0.0.1:8080 to use Concourse"
    kubectl port-forward --namespace default $POD_NAME 8080:8080
```

#### 1.2.3. Login with the following credentials

```
Username: concourse
Password: concourse
```

### Deploy Artifactory to kubernetes with helm

```
helm install --name artifactory --set artifactory.image.repository=docker.bintray.io/jfrog/artifactory-oss stable/artifactory
```
