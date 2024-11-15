## Installation

Add Victoria Metrics chart repository
```
helm repo add vm https://victoriametrics.github.io/helm-charts/
helm repo update
```
Install chart
```
helm install --dependency-update --create-namespace ut ut -n vm
```

## Grafana access

Get admin password
```
kubectl get secrets ut-grafana -n vm -o jsonpath='{.data.admin-password}' | base64 -d
```
Port forward Grafana service
```
kubectl port-forward services/ut-grafana 8080:80 -n vm
```
Go to [http://localhost:8080/login](http://localhost:8080/login) and login as admin
