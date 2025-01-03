# Crossplane

Crossplane is an open-source Kubernetes add-on that extends Kubernetes with the ability to provision and manage cloud infrastructure, services, and applications using kubectl, GitOps, or any tool that works with the Kubernetes API.

## Managing Providers

### Install the GCP Provider

```bash
crossplane provider install xpkg.upbound.io/upbound/provider-gcp:v0.42.0
```

### List Installed Providers

```bash
crossplane provider list
```

### Remove the GCP Provider

```bash
crossplane provider remove provider-gcp
```

## Managing Configurations

### Install the AWS Getting Started Configuration

```bash
crossplane config install xpkg.upbound.io/crossplane/getting-started-with-aws-example:v0.2.0
```

### List Installed Configurations

```bash
crossplane config list
```

### Remove the MyConfig Configuration

```bash
crossplane config remove my-config
```

## Working with Custom Resources (Claims)

### Apply a Database Claim from a YAML File

```bash
kubectl apply -f my-database-claim.yaml
```
(assuming a file named `my-database-claim.yaml` exists)

### Get a Database Claim in the default Namespace

```bash
kubectl get databases my-db -n default -o yaml
```

### List all Database Claims in the staging Namespace

```bash
kubectl get databases -n staging
```

### Delete a Database Claim in the dev Namespace

```bash
kubectl delete databases my-dev-db -n dev
```

## Debugging and Monitoring

### View Logs of the AWS Provider Controller

```bash
kubectl logs -n crossplane-system deployment/provider-aws -f
```

### Describe a Database Claim in the prod Namespace

```bash
kubectl describe databases prod-db -n prod
```

## Crossplane Help

### Crossplane General Help

```bash
crossplane --help
```

### Help on the provider install Command

```bash
crossplane provider install --help
```