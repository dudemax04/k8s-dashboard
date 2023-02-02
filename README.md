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

You can also access the dashboard using **https://NodeIP:Port**. You can find the node IP and port using below commands:

```shell
kubectl get pod -n kubernetes-dashboard  -o wide
kubectl get svc kubernetes-dashboard -n kubernetes-dashboard
```

**Here, I have used the port as 30001 in the code. You can modify the port as per your need.**

![image](https://user-images.githubusercontent.com/70281465/216355787-9017d321-b8c5-4173-a8c1-483dd44860c5.png)
