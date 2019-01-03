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
Follow the steps and log in to Concourse under http://127.0.0.1:8080.

### 2. Deploy Artifactory to kubernetes with helm

```
helm install --name artifactory --set artifactory.image.repository=docker.bintray.io/jfrog/artifactory-oss stable/artifactory
```

#### 2.1. Acces Artifactory
##### 2.1.1. Get the Artifactory URL by running these commands

NOTE: It may take a few minutes for the LoadBalancer IP to be available.
         You can watch the status of the service by running 'kubectl get svc -w nginx'
```
export SERVICE_IP=$(kubectl get svc --namespace default nginx -o jsonpath='{.status.loadBalancer.ingress[0].ip}')
echo http://$SERVICE_IP/
```

##### 2.1.2. Open Artifactory in your browser
Default credential for Artifactory:
```
user: admin
password: password
```
