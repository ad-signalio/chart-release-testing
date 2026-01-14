# Helm Chart Repository: chart-release-testing

Welcome to the landing page for our Helm chart repository!

## Overview
This repository hosts Helm charts for deploying and managing applications and infrastructure components in Kubernetes clusters. Here, you will find:
- Production-ready charts for internal and external services
- Documentation for each chart and its values
- Release notes and upgrade instructions

## Getting Started
To add this Helm repository to your local Helm client:

```
helm repo add ad-signalio https://<your-helm-repo-url>
helm repo update
```

Replace `<your-helm-repo-url>` with the actual URL where this repository is hosted.

## Available Charts
- See the `charts/` directory for a list of available charts.
- Each chart contains its own README with usage and configuration details.

## Contributing
- Please open issues or pull requests for improvements or new charts.
- Follow the contribution guidelines in the `docs/` directory.

## Support
For questions or support, contact the DevOps team at developers@ad-signal.io.

---

_This repository is maintained by Ad Signal. All charts are provided as-is and should be tested in a staging environment before production use._

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