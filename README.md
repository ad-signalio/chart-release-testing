# chart-release-testing

This repository contains a basic example Helm chart for Kubernetes.

## Chart: example-chart

A simple Helm chart that deploys an nginx application with the following components:

- **Deployment**: Runs a single replica of nginx
- **Service**: Exposes the deployment via ClusterIP
- **ServiceAccount**: Creates a service account for the pods
- **Ingress**: Optional ingress configuration (disabled by default)
- **HorizontalPodAutoscaler**: Optional autoscaling (disabled by default)

### Usage

#### Install the chart

```bash
helm install my-release ./example-chart
```

#### Customize values

You can override default values by creating a custom `values.yaml` file:

```bash
helm install my-release ./example-chart -f my-values.yaml
```

Or using `--set` flags:

```bash
helm install my-release ./example-chart --set replicaCount=3
```

#### Uninstall the chart

```bash
helm uninstall my-release
```

### Chart Structure

```
example-chart/
├── Chart.yaml          # Chart metadata
├── values.yaml         # Default configuration values
├── templates/          # Kubernetes manifest templates
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── serviceaccount.yaml
│   ├── ingress.yaml
│   ├── hpa.yaml
│   └── _helpers.tpl   # Template helpers
└── .helmignore        # Files to ignore when packaging
```

### Validation

Lint the chart:
```bash
helm lint example-chart
```

Test template rendering:
```bash
helm template example-chart example-chart
```