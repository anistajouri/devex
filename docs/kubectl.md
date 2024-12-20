# kubectl

`kubectl` is a command-line tool for interacting with Kubernetes clusters. It allows you to run commands against Kubernetes clusters to deploy applications, inspect and manage cluster resources, and view logs.

## Installation

To install `kubectl`, follow the instructions for your operating system:


### Linux

```sh
curl -LO "https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
```

## Basic Commands

Here are some basic `kubectl` commands to get you started:

### Get Cluster Information

```sh
kubectl cluster-info
```

### List Nodes

```sh
kubectl get nodes
```

### Get Pods

```sh
kubectl get pods
```

### Describe a Pod

```sh
kubectl describe pod <pod-name>
```

### Apply a Configuration

```sh
kubectl apply -f <file.yaml>
```

### Delete a Resource

```sh
kubectl delete -f <file.yaml>
```

## Advanced Commands

### Scale a Deployment

```sh
kubectl scale deployment <deployment-name> --replicas=<number>
```

### Rollout a Deployment

```sh
kubectl rollout restart deployment <deployment-name>
```

### Port Forwarding

```sh
kubectl port-forward <pod-name> <local-port>:<remote-port>
```

## Conclusion

`kubectl` is an essential tool for managing Kubernetes clusters. With its wide range of commands, you can perform various tasks to maintain and troubleshoot your applications running in Kubernetes.

For more detailed information, refer to the [official kubectl documentation](https://kubernetes.io/docs/reference/kubectl/overview/).

