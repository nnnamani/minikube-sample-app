# Minikube sample app

This repository is sample for deploying application on Kubernetes on minikube.

## Environments

- Host OS
  - MacOS Mojave
- Docker version
  - Docker Desktop: version 2.1.0.5
  - Engin: 19.03.5
- Kubernetes version
  - Client Version: v1.13.11
  - Server Version: v1.17.0
- minikube version
  - v1.6.2
  - driver
      - Uses Hyperkit installed with `Docker Desctop`

## How to deploy 

Workdir `minikube-sample-app`

1. Install minikube

```
$ brew install minikube
```

1. Create Cluster

```
$ minikube start --vm-driver=hyperkit
```

1. To use image  built on host os, loads docker environments from minikube

```
$ eval $(minikube docker-env)
```

1. Builds image

```
$ docker build ./app/ -t nnnamani/sample-app:v1
```

1. Deploy it

```
$ kubectl apply -f deployments.yaml
```

1. Open application

```
$ minikube service sample-app
```

