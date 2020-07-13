# Mesh GitOps
Repository for deploy Service Mesh cluster, microservices examples and objects through gitops

## Usage

### 1. Bootstrap (Helm3)

Deploy ArgoCD and the Namespaces / Services Accounts needed for this environment

```
helm template bootstrap/bootstrap-project/ | oc apply -f-
helm template bootstrap/argocd-operator/ | oc apply -f-
```

ArgoCD login with SSO of Openshift:

```
argocd login $(oc get route argocd-server --template='{{ .spec.host }}' -n labs-ci-cd):443 --sso --insecure
```

### 2. ServiceMesh Operator (ArgoCD)

Provision the Application in ArgoCD and let the gitops from ArgoCD deploy

```
helm template mesh-provision/ | oc apply -f-
```

This automatically provisions the mesh-operators and the mesh-controlplane objects into the cluster


