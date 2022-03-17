# apnmt-charts

## Add Repo
```
helm repo add apnmt https://apnmt.github.io/apnmt-charts/
```

## Create Namespace
```
kubectl create namespace apnmt
```

## Apnmt Cluster
```
helm install -n apnmt apnmt-cluster apnmt/apnmt-cluster --set 'kube-prometheus-stack.grafana.grafana\.ini.server.root_url=https://EMISSARY_INGRESS_URL/grafana'
helm uninstall -n apnmt apnmt-cluster
```

## Kafka
```
helm install -n apnmt apnmt-kafka apnmt/apnmt-kafka
helm uninstall -n apnmt apnmt-kafka
```

## Emissary ApiExt
```
helm install -n apnmt apnmt-emissary-apiext apnmt/apnmt-emissary-apiext
helm uninstall -n apnmt apnmt-emissary-apiext
```

## Emissary Tracing
```
helm install -n apnmt apnmt-emissary-tracing apnmt/apnmt-emissary-tracing
helm uninstall -n apnmt apnmt-emissary-tracing
```

## Emissary Ingress
```
helm install -n apnmt apnmt-emissary-ingress apnmt/apnmt-emissary-ingress
helm uninstall -n apnmt apnmt-emissary-ingress
```

## Jaeger
```
helm install -n apnmt apnmt-tracing apnmt/apnmt-tracing
helm uninstall -n apnmt apnmt-tracing
```

## Monitoring

```
helm install -n apnmt apnmt-monitoring apnmt/apnmt-monitoring --set 'kube-prometheus-stack.grafana.grafana\.ini.server.root_url=https://EMISSARY_INGRESS_URL/grafana'
helm uninstall -n apnmt apnmt-monitoring
```

## ELK Stack

```
helm install -n apnmt apnmt-elk apnmt/apnmt-elk
helm uninstall -n apnmt apnmt-elk
```

## Services
```
helm install -n apnmt apnmt-{serviceName} apnmt/{serviceName}
```

### Authservice
```
helm install -n apnmt apnmt-authservice-k8s apnmt/authservice-k8s
helm uninstall -n apnmt apnmt-authservice-k8s
```

### Appointmentservice
```
helm install -n apnmt apnmt-appointmentservice-k8s apnmt/appointmentservice-k8s
helm uninstall -n apnmt apnmt-appointmentservice-k8s
```   

## Access Application in minikube
If the Cluster is running in minikube, a tunnel must be used to access the endpoints through the emissary-ingress. 
```
minikube service apnmt-emissary-ingress -n apnmt
```
