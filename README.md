# Model Minion

This will be updated as the project progresses

[![Go CI](https://github.com/prehistoricpancake/model-minion/actions/workflows/ci.yml/badge.svg)](https://github.com/prehistoricpancake/model-minion/actions/workflows/ci.yml)
[![Go Report Card](https://goreportcard.com/badge/github.com/prehistoricpancake/model-minion)](https://goreportcard.com/report/github.com/prehistoricpancake/model-minion)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Go Version](https://img.shields.io/badge/Go-1.23-blue.svg)](https://golang.org/doc/devel/release.html)

> A Kubernetes operator for streamlined ML model deployment and management

## 🎯 Features

- 🚀 Automated ML model deployment to Kubernetes
- 🔄 Version management and rollback capabilities
- 📊 Built-in metrics and monitoring
- 🛡️ Resource management and scaling
- 🔍 Model health checks and auto-recovery

## 📋 Prerequisites

Before you begin, ensure you have met the following requirements:

- Go 1.23 or higher
- Docker Desktop
- Kubernetes cluster (minikube, kind, or cloud provider)
- kubectl configured with your cluster
- GitHub account for CI/CD integration

## 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/prehistoricpancake/model-minion.git

# Navigate to the project directory
cd model-minion

# Install dependencies
go mod download

# Run tests
go test ./...

# Build the operator
go build -o bin/model-minion cmd/operator/main.go

# Deploy to Kubernetes
kubectl apply -f deploy/manifests/
```

## 🏗️ Project Structure

```
.
├── .github/
│   └── workflows/          # GitHub Actions workflows
├── cmd/
│   └── operator/          # Main application entrypoint
├── internal/
│   └── controller/        # Operator controller logic
├── pkg/
│   └── apis/             # API definitions
├── api/
│   └── v1alpha1/         # CRD API versions
├── deploy/
│   └── manifests/        # Kubernetes deployment manifests
├── docs/                 # Documentation
├── test/                 # Test files
└── .gitignore
```

## 🔧 Development

### Setting up your development environment

1. Fork the repository
2. Create your feature branch:
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. Commit your changes:
   ```bash
   git commit -m 'feat: Add some amazing feature'
   ```
4. Push to your branch:
   ```bash
   git push origin feature/amazing-feature
   ```
5. Open a Pull Request

### Running Tests

```bash
# Run all tests
go test -v ./...

# Run tests with coverage
go test -v -coverprofile=coverage.out ./...
go tool cover -html=coverage.out
```

## 📚 Documentation

For detailed documentation, please refer to the [docs](./docs) directory:

- [Installation Guide](./docs/installation.md)
- [API Reference](./docs/api-reference.md)
- [Contributing Guidelines](./docs/CONTRIBUTING.md)
- [Architecture Overview](./docs/architecture.md)

## 📝 Custom Resource Definition (CRD)

```yaml
apiVersion: modelminion.io/v1alpha1
kind: MLModel
metadata:
  name: example-model
spec:
  modelUri: "s3://my-models/model.pkl"
  version: "1.0.0"
  resources:
    requests:
      memory: "1Gi"
      cpu: "500m"
    limits:
      memory: "2Gi"
      cpu: "1"
  scaling:
    minReplicas: 1
    maxReplicas: 5
```

## 🤝 Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

Please read our [Contributing Guidelines](./docs/CONTRIBUTING.md) before submitting a pull request.

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.

## 📬 Contact

Your Name - [@prehistoricpancake](https://github.com/prehistoricpancake)

Project Link: [https://github.com/prehistoricpancake/model-minion](https://github.com/prehistoricpancake/model-minion)
