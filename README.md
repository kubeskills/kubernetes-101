# Kubernetes 101 Course

Hands-on lesson notes and copy/paste commands to learn Kubernetes quickly. Use the linked lab environments to practice without setting up your own cluster.

## Lessons
- [Lesson 00: Cluster Basics](LESSON00/README.md) — control plane vs. workers, core components, and starter kubectl commands.
- [Lesson 01: Containers vs. Kubernetes](LESSON01/README.md) — running apps with Docker vs. Kubernetes, pods as the smallest unit, deployments as the larger unit.
- [Lesson 02: Cluster Architecture](LESSON02/README.md) — API resources, cluster info, nodes, and common discovery commands.
- [Lesson 03: Kubernetes API](LESSON03/README.md) — RESTful API model, RBAC/authn/authz chain, and querying objects directly.
- [Lesson 04: Deployments](LESSON04/README.md) — declarative rollouts, ReplicaSets, scaling, image updates, and rollbacks.
- [Lesson 05: Operators](LESSON05/README.md) — CRDs/controllers via Helm, Prometheus/Grafana operators, and pulling dashboards.
- [Lesson 06: Storage](LESSON06/README.md) — PersistentVolumes, PersistentVolumeClaims, and mounting data into pods.

## How to Use
- Open a lesson README, skim the notes, then run the commands in a sandbox (KillerCoda Kubernetes playground works well).
- Keep `kubectl` handy; for operator lessons you’ll also want `helm` installed.
- Most commands assume the shorthand alias `k=kubectl` for speed.

## Practice Links
- Free course community: https://community.kubeskills.com/c/101-course
- KillerCoda Kubernetes playground: https://killercoda.com/playgrounds/scenario/kubernetes
