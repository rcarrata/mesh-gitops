# ArgoCD Operator Helm Deploy

ArgoCD Helm Chart customises and deploys the [ArgoCD](https://argoproj.github.io/argo-cd/getting_started/) project using the [Operator](https://argocd-operator.readthedocs.io/en/latest/) written by Red Hat.

## Installing the chart

To install the chart:

```bash
$ helm template -f argocd-operator/values.yaml argocd-operator | oc apply -f-
```

The above command creates objects with default naming convention and configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

## Configuration
The following table lists the configurable parameters of the ArgoCD chart and their default values. For more detailed overview of what's configurable, checkout the [ArgoCD Operator Docs](https://argocd-operator.readthedocs.io/en/latest/reference/argocd/)

| Parameter                                        | Description                                                  | Default                               |
| ------------------------------------------------ | -------------------------------------------------------------| ------------------------------------- |
| `namespace`                                      | Project name to deploy DevEx tools                           | `cicd`                          |
| `name`                                           | Project name for argocd server                               | `argocd`                         |
| `instancelabel`                                  | Unique identifier for argocd default label                   | `rcarrata-argo`     |
