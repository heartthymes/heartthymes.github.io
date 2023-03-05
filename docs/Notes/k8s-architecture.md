 ## K8S Architecture
 
>Date: 2022-04-01   
>Category: [Kubernetes](00Kubernetes.md)  
>Tags: #kubernetes #k8s #cloud #containers  

![k8s-architecture](k8s-architecture.png)

Kubernetes allows to deploy any app that runs on VM by [containerizing](https://www.youtube.com/watch?v=cjXI-yxqGTI) it and it's components.

On the very high level k8s provides hosts for running workloads using containers and a set of management hosts called masters for the API. All hosts are connected withing overlaying network and container-to-container routing. Apps deployed to k8s are discoverable withing the network and exposed via load balancers. State of the cluster is stored in a key/value store [etcd](etcd.md) which runs withing master instances.

Kubernetes [scheduler](k8s-scheduler.md) is in charge of health check of the all off the components. 

Kubernetes offer two types of scalability:
- scaling resources using [Horizontal Pod Autoscaler](horizontal-pod-autoscaler.md) (watches resource consumption constantly)
- scale the container cluster itself by adding and removing hosts depending on resource requirements

---
- [kubernetes-beginneers-guide](kubernetes-beginneers-guide.md)