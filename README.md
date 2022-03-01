# Zen

An example monorepo project with NestJS, Dapr, Docker and Kubernetes

# Pre-requisites: 
Have a working Kubernetes Cluster

# Reproducing Steps:
Install the Dapr CLI and run the following command to create the required dapr components in your cluster [dapr]("https://docs.dapr.io/getting-started/")

```
# Deploy Dapr to the cluster
dapr init -k
```

# Cleanup
```
kubectl delete -f k8s/
dapr uninstall -k
```

