```bash
helm upgrade -i prometheus prometheus-community/kube-prometheus-stack -n monitoring --create-namespace \
--set nameOverride="orgname" \
--set grafana.serviceMonitor.labels.release=prometheus \
--set grafana.image.tag=10.3.3 \
--set grafana.adminPassword="pass" \
--set kube-state-metrics.prometheus.monitor.enabled=true \
--set kube-state-metrics.prometheus.monitor.additionalLabels.release=prometheus
```