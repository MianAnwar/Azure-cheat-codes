# 1. Create the resource group
```
az group create --name kubernetes-grp --location northeurope
```

# 2. Then create the cluster
```
az aks create --resource-group kubernetes-grp --name appcluster --node-count 1 --enable-addons monitoring --generate-ssh-keys
```

# 3. If you don't have the kubectl tool installed locally, then install the CLI
```
az aks install-cli
```

# 4. Then download the credentials so that the kubectl tool can use the kubernetes cluster
```
az aks get-credentials --resource-group kubernetes-grp --name appcluster
```

# 5. To get the nodes in the cluster
```
kubectl get nodes
```

#6. We can then deploy our application via the kubectl command
```
kubectl apply -f deployment.yml
kubectl apply -f service.yml
```

# 7. We can delete the resource group
```
az group delete --name kubernetes-grp
```
