# hr-helm-charts

This repository contains Helm charts migrated to `hr-helm-charts` (`main`) from `hr-employee-service` (`development`).

## Available charts

- `charts/microservice-base`: reusable Helm **library chart** with shared templates for service accounts, configmaps, deployments, services, ingresses, and HPAs.
- `charts/hr-employee-service`: application chart for the HR Employee Service that consumes `microservice-base`.

## Package and validate

```bash
helm dependency update charts/hr-employee-service
helm lint charts/microservice-base
helm lint charts/hr-employee-service
helm template hr-employee-service charts/hr-employee-service
```
