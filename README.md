# Helm Charts

This repository hosts packaged [Helm](https://helm.sh/) charts for the `waTeim` projects.
Charts are published automatically to this repository when changes are merged into the
[`waTeim/k8ev-kit`](https://github.com/waTeim/k8ev-kit) source repo.

The repository is available at:

https://wateim.github.io/helm-charts

## Adding the Repository

Add this Helm repository to your local environment:

```bash
helm repo add wateim https://wateim.github.io/helm-charts
helm repo update
```

## Available Charts

- **siren** – Tools for managing Lighthouse validator API access
- **eth-validator** – Deployment of an Ethereum validator + execution/consensus clients

Check the available versions with:

```bash
helm search repo wateim
```

## Installing a Chart

Example (siren):

```bash
helm install my-siren wateim/siren --version <chart_version>
```

Example (eth-validator):

```bash
helm install my-validator wateim/eth-validator --version <chart_version>
```

Replace `<chart_version>` with a version from `helm search repo`.

## How This Repo Is Updated

- Charts live in [waTeim/k8ev-kit](https://github.com/waTeim/k8ev-kit) under the
  `siren/` and `eth-validator/` subdirectories.
- When a pull request from **develop → master** is merged in that repo:
  - The workflow checks if the `version:` in each `Chart.yaml` has changed.
  - If so, the chart is packaged and published here.
  - If the version is unchanged, nothing new is published.

## Contributing

To contribute to the charts themselves:
1. Open pull requests against [waTeim/k8ev-kit](https://github.com/waTeim/k8ev-kit).
2. Bump the `version:` field in the `Chart.yaml` whenever you want to trigger a new release.

## License

[Apache 2.0](LICENSE) (adjust if your project uses a different license)
