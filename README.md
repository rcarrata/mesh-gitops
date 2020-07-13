# Mesh GitOps
Repository for deploy Service Mesh cluster, microservices examples and objects through gitops


## Deployment

```
helm template bootstrap/bootstrap-project/ | oc apply -f-
helm template bootstrap/argocd-operator/ | oc apply -f-
```


