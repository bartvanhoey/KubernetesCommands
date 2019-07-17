# AZ CLI and Kubectl Commands

## Azure Container Service (AKS)

### Create resource group and K8S cluster in AKS

| Command                                                                                        |               Description                                    |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`az group create -n <resource-group-name> -l westeurope`                                        | create a new resource group                                  |
|`az aks create -n <cluster-name> -g <resource-group-name> -c 1 -k 1.7.7`                        | create a new 1 node K8S cluster with version 1.7.7           |

### Overview your K8S clusters in AKS

| Command                                                                                        |               Description                                    |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`az aks list -o table`                                                                          | get list of all k8s clusters under your subscription         |

### Retrieve kubeconfig info from cluster and merge into kubeconfig on local machine

| Command                                                                                        |               Description                                    |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`az aks get-credentials --resource-group <resource-group-name> --name <cluster-name>`           | merge your K8S cluster into local kubeconfig                 |
|`az aks get-credentials -n <cluster-name> -g <resource-group-name>`                             | merge your K8S cluster into local kubeconfig                 |

### Open K8S dashboard locally

| Command                                                                                        |               Description                                    |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`az aks browse --resource-group  <resource-group-name> --name <cluster-name>`                   | open dashboard Azure kubernetes cluster                      |
|`az aks browse -n <cluster-name> -g <resource-group-name>`                                      | open dashboard Azure kubernetes cluster                      |

### Increase node count in your K8S cluster

| Command                                                                                        |               Description                                    |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`az aks scale -n <cluster-name> -g <resource-group-name> -c 10`                                 | increase node count to 10 in your agent pool                 |

### Show current Control Plane and Agent Pool K8S version and available upgrade versions

| Command                                                                                        |               Description                                    |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`az aks get-versions -n <cluster-name> -g <resource-group-name>`                                | shows current K8S version and available upgrade versions     |

### Upgrade K8S cluster version

| Command                                                                                        |               Description                                    |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`az aks upgrade -n <cluster-name> -g <resource-group-name> -k 1.8.3`                            | upgrades in a rolling fashion                                |

### Kubectl Commands

### Nodes

| Command                                                                                        |               Action                                         |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`kubectl get nodes`                                                                             | get nodes                                                    |

### Pods

| Command                                                                                        |               Action                                         |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`kubectl get pods`                                                                              | get pods                                                     |
|`kubectl get pods --all-namespaces`                                                             | get all pods in all namespaces                               |

### Deployments

| Command                                                                                        |               Action                                         |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`kubectl apply -f deployment.yaml`                                                              | deploy to kubernetes cluster                                 |
|`kubectl get deployments`                                                                       | get deployments of a kubernetes cluster                      |

### Services

| Command                                                                                        |               Action                                         |
|------------------------------------------------------------------------------------------------|--------------------------------------------------------------|
|`kubectl get services`                                                                          | get services in a kubernetes cluster                         |
|`kubectl delete svc <service-name>.`                                                            | delete a service by name                                     |
|`kubectl get pods`                                                                              | get pods                                                     |

## Howto connect to K8S dashboard in your local Docker Engine

1. Docker -> Settings -> Kubernetes -> Enable Kubernetes [Apply]
2. Open a command prompt and enter `kubectl describe secret`
3. Copy token
4. `kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v1.10.1/src/deploy/recommended/kubernetes-dashboard.yaml`
5. `kubectl proxy`
6. `Navigate to <http://localhost:8001/api/v1/namespaces/kube-system/services/https:kubernetes-dashboard:/proxy/#!/login>
7. Choose Token in Kubernetes dashboard and paste in token
