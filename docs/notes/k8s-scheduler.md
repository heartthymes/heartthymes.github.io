 ## k8s-scheduler
 
>Date: 2022-04-01  
>Category: [00Kubernetes](links/00Kubernetes.md)
>Tags: #kubernetes #k8s #containers 

When the number of replicas is set to more than one each instance is scheduled in multiple hosts and when one host becomes unavailable all of the containers that were running in that container are scheduled in any of the remaining hosts.

With the introduction of [cluster-federation-capability](notes/cluster-federation-capability.md), scheduler can manage a collection of Kubernetes clusters on the different data centers using a single API endpoint.

---
- [k8s-architecture](notes/k8s-architecture.md)