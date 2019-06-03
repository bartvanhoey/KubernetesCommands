# Kubernetes Command

## Pods

| Command                                                                                        |               Action                                         |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`kubectl get pods`                                                                              | get pods                                                     |

## Deployments

| Command                                                                                        |               Action                                         |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`kubectl apply -f deployment.yaml`                                                              | deploy to kubernetes cluster                                 |
|`kubectl get deployments`                                                                       | get deployments of a kubernetes cluster                      |

## Services

| Command                                                                                        |               Action                                         |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`kubectl get services`                                                                          | get services in a kubernetes cluster                         |
|`kubectl delete svc <service-name>.`                                                            | delete a service by name                                     |
|`kubectl get pods`                                                                              | get pods                                                     |


## Azure Container Service

| Command                                                                                        |               Action                                         |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`az aks get-credentials --resource-group <resource-group-name> --name <cluster-name>`           | get the credentials kubernetes cluster in Azure              |
|`az aks browse --resource-group  <resource-group-name> --name <cluster-name>`                   | open dashboard Azure kubernetes cluster                      |
