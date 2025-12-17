# Kubernetes 101 Course

[Kubernetes 101 Course - FREE](https://community.kubeskills.com/c/101-course)

## Kubernetes Cluster Architecture

- [Click Here to view the lesson](https://community.kubeskills.com/c/101-course/sections/6275/lessons/16661)


```bash
alias

# list pods, services, and daemonsets in all namespaces
k get po,svc,ds -A

# list nodes in the cluster
k get no

# list authentication config for cluster
k config view

# list all resources avaiable
k api-resources

# list the cluster address and CoreDNS IP and port
k cluster-info

# list the control plane component versions, and 
k upgrade plan

# list the events happening in the cluster
k get events -A

```
