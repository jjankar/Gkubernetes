## The google cloud kubernetes platform for micro-services

### Deploy Concourse to kubernetes with helm

```
helm install stable/concourse --name concourse
```

### Deploy Artifactory to kubernetes with helm

```
helm install --name artifactory --set artifactory.image.repository=docker.bintray.io/jfrog/artifactory-oss stable/artifactory
```
