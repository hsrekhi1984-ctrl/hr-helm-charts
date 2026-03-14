# hr-helm-charts

Reusable Helm chart setup for HR microservices using a single base chart and per-service values files.

## Structure

- `helm/microservice-base`: reusable base chart that renders common Kubernetes resources:
  - Deployment
  - Service
  - Ingress
  - HorizontalPodAutoscaler
  - NetworkPolicy
  - PodDisruptionBudget
  - ServiceAccount
  - ServiceMonitor
  - Secret
- Service-specific values files:
  - `helm/hr-employee-service/values.yaml`
  - `helm/hr-payroll-service/values.yaml`
  - `helm/hr-notification-service/values.yaml`
  - `helm/hr-leave-service/values.yaml`
  - `helm/hr-frontend/values.yaml`

## Install examples

```bash
helm install hr-employee-service ./helm/microservice-base -f ./helm/hr-employee-service/values.yaml
helm install hr-payroll-service ./helm/microservice-base -f ./helm/hr-payroll-service/values.yaml
helm install hr-notification-service ./helm/microservice-base -f ./helm/hr-notification-service/values.yaml
helm install hr-leave-service ./helm/microservice-base -f ./helm/hr-leave-service/values.yaml
helm install hr-frontend ./helm/microservice-base -f ./helm/hr-frontend/values.yaml
```

## Validate

```bash
helm lint ./helm/microservice-base
helm template hr-employee-service ./helm/microservice-base -f ./helm/hr-employee-service/values.yaml
```
