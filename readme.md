# hr-helm-charts

This repository contains Helm charts migrated to `hr-helm-charts` (main) from `hr-employee-service` (`development` branch).

## Available charts

- `charts/hr-employee-service`: chart for deploying the HR Employee Service.

## Package and validate

```bash
helm lint charts/hr-employee-service
helm template hr-employee-service charts/hr-employee-service
```
