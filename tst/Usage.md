# Usage

Once you've deployed your services to Kubernetes in the "ai" namespace, you can perform various tasks and operations using `kubectl` and other Kubernetes resources.

## Get All Pods

To list all the pods running in the "ai" namespace:

```bash
kubectl get po -n ai
```
## List Persistent Volume Claims (PVCs)
To list the Persistent Volume Claims (PVCs) in the "ai" namespace:
```bash
kubectl get pvc -n ai
```
## Exec into a Pod
To access a shell within a pod for debugging or running commands:
```bash
kubectl exec -it <pod_name> -n ai -- /bin/bash
Make sure to replace <pod_name> with the actual name of the pod you want to access.
```
## Scaling Deployments
You can scale your deployments up or down based on your requirements. For example, to scale a deployment named "spark-deployment" to 3 replicas:

```bash
kubectl scale deployment spark-deployment --replicas=3 -n ai
```
## Monitor Cluster Events
To view the cluster events and monitor what's happening in the "ai" namespace, you can use:

```bash
kubectl get events -n ai
```
## Resource Utilization
Check the resource utilization of your pods and nodes:

```bash
kubectl top pods -n ai
kubectl top nodes -n ai
```
## Logs
View the logs of a specific pod:

```bash
kubectl logs <pod_name> -n ai
Replace <pod_name> with the actual pod name.
```
