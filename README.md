# k8s-dashboard
Kubernetes Dashboard is a general purpose, web-based UI for Kubernetes clusters. It allows users to manage applications running in the cluster and troubleshoot them, as well as manage the cluster itself.

### Install

To deploy Dashboard, execute following command:

```shell
kubectl apply -f https://raw.githubusercontent.com/dudemax04/k8s-dashboard/main/k8sdashboard.yaml
```
### Create Token

You are required to provide a token to login to the dashboard. Use below command to create a token:

```shell
kubectl -n kubernetes-dashboard create token admin-user
```

### Access

To access Dashboard from your local workstation you must create a secure channel to your Kubernetes cluster. Run the following command:

```shell
kubectl proxy
```
Now access Dashboard at:

[`http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/`](
http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/).
