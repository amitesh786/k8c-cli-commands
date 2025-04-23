# 🚀 Minikube & kubectl Quickstart Guide

This guide provides a concise and practical set of commands to get you up and running with Kubernetes(k8c) locally using Minikube and kubectl. Whether you're setting up your environment, deploying applications like NGINX or MongoDB, or monitoring cluster metrics this cheat sheet covers the essentials for development and testing on a local Kubernetes cluster.

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

## Delete deployments
- `kubectl delete deployment mongo-depl`
- `kubectl delete deployment nginx-depl`

## Create/Edit config file
- `vim nginx-deployment.yaml`
- `kubectl apply -f nginx-deployment.yaml`
- `kubectl get pod`
- `kubectl get deployment`

## Delete with config file
- `kubectl delete -f nginx-deployment.yaml`

## 📊 Metrics
- `kubectl top`
Note: The `kubectl top` command returns current CPU and memory usage for a cluster’s pods or nodes.
