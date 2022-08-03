# Cluster Application and Service Bootstrapping

This directory containes the resources, in numbered order, that should be deployed to the cluster to ensure full functionality of all other services in the [workloads](../workloads/) directory.

# Letting ArgoCD Manage the bootstrapping services

After the initial deployment of everything, we can have ArgoCD manage the updates for the bootstrapped services, as well as itself.

```bash
kubectl apply -k
```
