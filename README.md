# Helm Chart for Node.js Server

This Helm chart deploys a Node.js server along with a MongoDB database using Bitnami’s MongoDB subchart. It supports service exposure, ingress configuration, and Kubernetes secrets for environment configuration.

## Features

- Deploy a Node.js server container
- Configurable environment variables via Helm or existing Kubernetes Secrets
- MongoDB deployment using Bitnami chart
- Optional Ingress with TLS support
- Resource requests and limits
- Service exposure with configurable port

## Structure

```plaintext
.
├── Chart.yaml
├── values.yaml
├── templates/
├── NOTES.txt
└── README.md
```

## Configuration

You can configure the deployment by editing the `values.yaml` file or by using the `--set` flag when installing the chart.

### Example with `--set`:

```bash
helm install my-nodejs-server . \
  --set image.tag="latest" \
  --set secrets.enabled=true \
  --set secrets.existingSecret="my-secret" \
  --set service.port=3000
```

## Getting Started

### 1. Clone the Repository

First, clone this repository to your local machine:

```bash
git clone https://github.com/mariansmolii/nodejs-helm-chart.git
cd nodejs-helm-chart
```

### 2. Install Dependencies

```bash
helm dependency update
```

### 3. Install the Chart

```bash
helm install my-nodejs-server .
```

### 4. Cleanup

```bash
helm uninstall my-nodejs-server
```
