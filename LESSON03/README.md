# Kubernetes 101 Course

[Kubernetes 101 Course - FREE](https://community.kubeskills.com/c/101-course)

---

## Kubernetes API

- API is REST-like: one consistent interface to create/read/update/delete cluster objects.
- Access is gated by RBAC and the authn/authz/admission chain; clients must present certs/credentials.
- API abstracts underlying infra (VMware, Azure, AWS, etc.) so kubectl commands work the same regardless of provider.
- Common resources exposed: pods, services, deployments, replica sets, namespaces, roles/rolebindings, cluster roles/bindings, network policies, and more.
- Images live in registries; you pull artifacts from a central store and run them via the API on any cluster.

### Explore the API (KillerCoda sandbox)

```bash
# view raw pod objects from the API
kubectl get --raw /api/v1/pods | jq

# compare to the usual list output
kubectl get pods -A

# find control plane endpoint
kubectl cluster-info

# (example) curl the API directly - needs client certs/keys to auth
curl -k https://<control-plane-ip>:6443

# list enabled admission plugins (requires kube-system context and correct pod name)
kubectl exec -n kube-system kube-apiserver-control-plane -- \
  kube-apiserver --help | grep "enable-admission-plugins"

# check control plane component health
kubectl get componentstatuses
```
