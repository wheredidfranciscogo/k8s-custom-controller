# Kubernetes Custom Controller

## Overview
This project is a **Kubernetes Custom Controller** built using **Kubebuilder** and **Go**. It extends Kubernetes by managing custom resources (CRDs) to automate specific operational tasks within a cluster.

## Features
- Implements a Kubernetes controller using the **controller-runtime** framework.
- Watches and reconciles custom resources (CRDs).
- Can be deployed as a Kubernetes-native application.
- Designed for **GitHub** and **GitLab** visibility.

## Getting Started
### Prerequisites
- **Go** (>= 1.20)
- **Kubebuilder** (Installed & configured)
- **Docker** (for containerization)
- **Kubernetes cluster** (Minikube, Kind, or a cloud provider like GKE, EKS, or AKS)

### Installation
Clone the repository:
```bash
# If using GitHub
git clone https://github.com/franciscoarrieta/k8s-custom-controller.git
# If using GitLab
git clone https://gitlab.com/franciscoarrieta/k8s-custom-controller.git
cd k8s-custom-controller
```

Initialize the project (already done if using Kubebuilder):
```bash
kubebuilder init --domain example.com --repo github.com/franciscoarrieta/k8s-custom-controller
```

### Creating APIs and Controllers
To create a new API and its controller, run:
```bash
kubebuilder create api --group sample --version v1 --kind CustomResource
```

This will generate the necessary boilerplate code to define a **Custom Resource Definition (CRD)** and its corresponding controller logic.

### Building and Running Locally
To run the controller locally:
```bash
make run
```

### Deploying to Kubernetes
Build and push the container image:
```bash
docker build -t ghcr.io/franciscoarrieta/k8s-custom-controller:latest .
docker push ghcr.io/franciscoarrieta/k8s-custom-controller:latest
```

Apply the CRD and deploy the controller:
```bash
make install
make deploy
```

### Contributing
- Fork the repository
- Create a feature branch (`git checkout -b feature-name`)
- Commit your changes (`git commit -m "Add new feature"`)
- Push the branch (`git push origin feature-name`)
- Open a pull request

### License
This project is licensed under the MIT License.

### Future Enhancements
- Implement additional reconcilers
- Add Prometheus metrics for monitoring
- Improve logging and error handling

