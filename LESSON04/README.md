# Kubernetes 101 Course

[Kubernetes 101 Course - FREE](https://community.kubeskills.com/c/101-course)

---

## Deployments

- Deployments describe desired state for stateless apps (image, replica count) and Kubernetes keeps them declarative and continuously reconciled.
- Creating a deployment automatically creates a ReplicaSet that maintains the requested number of pods; deleting pods triggers replacements.
- Rollouts create new ReplicaSets on changes (e.g., image updates) and allow rollback to previous revisions.
- Control plane and etcd use leader election for HA; services load balance traffic across replica pods.

### Handy commands
- Create: `kubectl create deploy nginx --image=nginx`
- Inspect: `kubectl get deploy`, `kubectl get rs`, `kubectl get pods`
- Scale: `kubectl scale deploy nginx --replicas=5`
- Update image (trigger rollout): `kubectl set image deploy/nginx nginx=nginx:1.14.2 --record`
- Rollout history/status: `kubectl rollout history deploy/nginx`, `kubectl rollout status deploy/nginx`
- Roll back: `kubectl rollout undo deploy/nginx --to-revision=1`

### Practice links
- [Change Deployment Image - Killercoda Lab](https://killercoda.com/chadmcrowell/course/cka/change-deployment-image)
- [Create and Scale Apache Deployment - Killercoda Lab](https://killercoda.com/chadmcrowell/course/cka/create-apache-deployment)
- [Rollback a Deployment - Killercoda Lab](https://killercoda.com/chadmcrowell/course/cka/rollback-deployment)
- [Change Rollout Strategy - Killercoda Lab](https://killercoda.com/chadmcrowell/course/cka/change-rollout-strategy)