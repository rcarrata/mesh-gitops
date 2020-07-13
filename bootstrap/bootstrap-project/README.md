# Bootstrap

Bootstrap chart helps you to create Openshift projects, service accounts and rolebindings.

## Installing the chart

To install the chart:

```bash
$ helm template -f bootstrap-project/values.yaml bootstrap-project | oc apply -f-
```

The above command creates objects with default naming convention and configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

## Configuration
The following table lists the configurable parameters of the Bootstrap chart and their default values.

| Parameter                                        | Description                                                  | Default                               |
| ------------------------------------------------ | -------------------------------------------------------------| ------------------------------------- |
| `ci_cd_namespace`                                | Project name to deploy DevEx tools                           | `cicd`                               |
| `test_namespace`                                 | Project name for test environment                            | `test`                                |
| `serviceaccounts.name`                           | The name of the service account that will be created         | `dummy-sa`                            |


```bash
$ helm template -f bootstrap-project/my-values.yaml bootstrap-project | oc apply -f-
```

## Kudos

This is a forked and customized helm chart, the original one is in https://github.com/rht-labs/helm-charts maintained by the fine folks of the rht-labs.
