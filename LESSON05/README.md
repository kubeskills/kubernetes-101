# Kubernetes 101 Course

[Kubernetes 101 Course - FREE](https://community.kubeskills.com/c/101-course)

---


## Operators

- Operators extend Kubernetes with custom controllers plus Custom Resource Definitions (CRDs) to manage complex apps (e.g., Prometheus, Grafana) declaratively.
- Helm can install operators and their CRDs in one go, bundling many resources into a single chart install.
- Prometheus Operator scrapes cluster metrics; Grafana Operator deploys dashboards to visualize them.
- Init containers often prepare state before main containers start; watch operator pods with `-w` to follow readiness.

### Handy commands
- Add repo for Prometheus Operator chart: `helm repo add bitnami https://charts.bitnami.com/bitnami && helm repo update`
- Install Prometheus Operator: `helm install prom-operator bitnami/kube-prometheus`
- Watch resources: `kubectl get pods -w`
- Customize Helm values (e.g., Grafana service type NodePort) via `values.yaml`; install with `helm install grafana-operator bitnami/grafana-operator -f values.yaml`
- List services and node ports: `kubectl get svc`
- Fetch Grafana admin password: `kubectl get secret grafana-admin-credentials -o jsonpath='{.data.grafana-admin-password}' | base64 -d`
- Roll out dashboards by importing IDs from Grafana.com (e.g., `1860` for Node Exporter Full) after setting Prometheus as a data source.

### Practice links
- [Install a Database Operator in Kubernettes](https://killercoda.com/chadmcrowell/course/cka/database-operator)
- Grafana community dashboards: https://grafana.com/grafana/dashboards/
