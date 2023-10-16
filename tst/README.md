# AI Namespace Deployment : 
This guide provides instructions for deploying a solution to Kubernetes (K8s) within your repository. We'll cover creating a Kubernetes namespace and deploying three different services: Spark, Cassandra, and Python Server.

## Prerequisites

Before you begin, ensure you have the following prerequisites:

- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/) installed.
- Access to a running Kubernetes cluster.

## Step 1: Create a Kubernetes Namespace

You can create a custom namespace with a name of your choice. In this example, we'll create a namespace named "ai."

```bash
kubectl create ns ai
```
## Step 2: Deploy Spark
Create Persistent Volume (PV) and Persistent Volume Claim (PVC)
```bash
kubectl apply -f spark/manifest/pv.yml -n ai
kubectl apply -f spark/manifest/pvc.yml -n ai
```
Create a Service (svc)
```bash
kubectl apply -f spark/manifest/svc.yml -n ai
```
Deploy Spark
```bash
kubectl apply -f spark/manifest/deploy -n ai
```
## Step 3: Deploy Cassandra
Create Persistent Volume (PV) and Persistent Volume Claim (PVC)
```bash
kubectl apply -f cassandra/manifest/pv.yml -n ai
kubectl apply -f cassandra/manifest/pvc.yml -n ai
```
Create a Service (svc)
```bash
kubectl apply -f cassandra/manifest/svc.yml -n ai
```
Deploy Cassandra

```bash
kubectl apply -f cassandra/manifest/deploy -n ai
```
## Step 4: Deploy Python Server
Create Persistent Volume (PV) and Persistent Volume Claim (PVC)
```bash
kubectl apply -f python-server/manifest/pv.yml -n ai
kubectl apply -f python-server/manifest/pvc.yml -n ai
```
Deploy Python Server
```bash
kubectl apply -f python-server/manifest/deploy -n ai
```
That's it! You've successfully deployed Spark, Cassandra, and the Python Server to your Kubernetes cluster in the "ai" namespace. You can access these services as needed.

