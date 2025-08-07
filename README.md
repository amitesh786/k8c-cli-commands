# Minikube & kubectl Quickstart Guide

This document offers a concise and practical set of commands to help you get started with Kubernetes (k8s) on your local machine using Minikube and kubectl. It covers essential tasks such as environment setup, application deployment (e.g., NGINX, MongoDB), and basic monitoring. This guide is ideal for development and testing within a local Kubernetes cluster.

## Install Prerequisites
- Ensure you have [Homebrew](https://brew.sh) installed on macOS.

## Install Hyperkit and Minikube
- `brew update`
- `brew install hyperkit`
- `brew install minikube`

## Check tools
- `kubectl`
- `minikube`

## Create Minikube Cluster
- `minikube start --vm-driver=hyperkit`
- `kubectl get nodes`
- `minikube status`
- `kubectl version`

## Delete Cluster and Restart (debug mode)
- `minikube delete`
- `minikube start --vm-driver=hyperkit --v=7 --alsologtostderr`
- `minikube status`

## Basic kubectl commands
- `kubectl get nodes`
- `kubectl get pod`
- `kubectl get services`
- `kubectl create deployment nginx-depl --image=nginx`
- `kubectl get deployment`
- `kubectl get replicaset`
- `kubectl edit deployment nginx-depl`

## Debugging
- `kubectl logs {pod-name}`
- `kubectl exec -it {pod-name} -- bin/bash`

## Create Mongo deployment
- `kubectl create deployment mongo-depl --image=mongo`
- `kubectl logs mongo-depl-{pod-name}`
- `kubectl describe pod mongo-depl-{pod-name}`

## Create/Edit config file
- `vim nginx-deployment.yaml`
- `kubectl apply -f nginx-deployment.yaml`
- `kubectl get pod`
- `kubectl get deployment`

## Delete deployments
- `kubectl delete deployment mongo-depl`
- `kubectl delete deployment nginx-depl`

## Metrics
- `kubectl top`
Note: The `kubectl top` command returns current CPU and memory usage for a cluster’s pods or nodes.

## Delete with config file
- `kubectl delete -f nginx-deployment.yaml`

## Developer Setup
- Clone the repository:
- git clone `https://github.com/amitesh786/k8c-cli-commands.git`

## Author Amitesh Singh – [GitHub](https://github.com/amitesh786)
- Contributions and suggestions for improvement are welcome.
