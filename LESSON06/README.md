# Kubernetes 101 Course

[Kubernetes 101 Course - FREE](https://community.kubeskills.com/c/101-course)

---

## Storage

- PersistentVolumes (PVs) provide cluster storage (hostPath, NFS, cloud provisioners); PersistentVolumeClaims (PVCs) request that storage for pods.
- Pods are ephemeral, but PVCs keep their bound PV so data survives pod restarts/rescheduling.
- Access modes matter (e.g., `ReadWriteOnce`), and storage classes define the provisioner/backend.
- Mount the PVC in your pod spec via `volumes` and `volumeMounts`; the claim name must match.

### Handy commands
- Inspect storage classes/PVs/PVCs: `kubectl get sc`, `kubectl get pv,pvc`
- Create PV/PVC from YAML (hostPath example): apply from `https://k8s.io/examples/pods/storage/` samples or a here-doc with `kind: PersistentVolume` and `PersistentVolumeClaim`
- Verify binding: `kubectl get pv,pvc` (look for `STATUS=Bound`)
- Create a pod using the claim: in pod spec `volumes: { name: pv-storage, persistentVolumeClaim: { claimName: pv-claim } }` and mount at desired path
- Check data persists: write a file, delete the pod, recreate/replace the pod, and confirm the file remains via `kubectl exec ... cat /path/to/file`

### Practice links
- [PersistentVolumes - Killercoda Lab](https://killercoda.com/chadmcrowell/course/cka/persistent-volumes)
- [NFS Storage in Kubernetes - Killercoda Lab](https://killercoda.com/chadmcrowell/course/cka/nfs-vol)
- PV example YAML: https://k8s.io/examples/pods/storage/pv-volume.yaml
- PVC example YAML: https://k8s.io/examples/pods/storage/pv-claim.yaml
