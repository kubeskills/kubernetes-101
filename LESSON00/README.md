# Kubernetes 101 Course

[Kubernetes 101 Course - FREE](https://community.kubeskills.com/c/101-course)

---


## Lesson Overview

- Assumes you already know Linux basics and how containers work (Docker commands not memorization-heavy).
- Focuses on how Kubernetes uses container images, not on building images or Docker Compose.
- Core mental model: a cluster has a control plane (brains) and worker nodes (run workloads).

## Control Plane (Brains)

- Runs Kubernetes itself: pod creation, lifecycle management, and the API that exposes resources/objects.
- Key components: API server, scheduler, controller manager, etcd datastore.

## Worker Nodes (Run Workloads)

- Host your pods/deployments after the scheduler assigns them.
- Components:
  - Container runtime (containerd) runs the containers.
  - Kubelet checks in with the control plane and reports pod health/status.
  - Kube-proxy programs iptables rules to route cluster traffic (name stuck from when it proxied).
- Example flow: `kubectl get pods` reaches the kubelet for pod info on worker nodes and returns the list.

## Practice Lab

- Use the free KillerCoda lab environment: sign up at [killercoda.com](https://killercoda.com) with Google/GitHub.
- Provides a ready cluster so you can practice without building one; we may still toy locally (e.g., with kind) as supplemental work.

## Useful Commands

- `kubectl version --short` — quick control plane and kubectl version check.
- `kubectl get nodes -o wide` — see cluster nodes and key IP/OS details.
- `kubectl get pods -A` — list all pods in every namespace.
- `kubectl describe node <name>` — view node capacity, conditions, labels, and running pods.
- `kubectl api-resources` — list all available Kubernetes resource types.
- `kubectl get events -A --sort-by=.lastTimestamp` — see recent cluster activity ordered by time.

Kubectl cheat sheet from Kubeskills: https://subscribe.kubeskills.com

