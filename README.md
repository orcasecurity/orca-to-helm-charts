# Installation

1. Create Kubernetes namespace
```
kubectl create ns threatoptix
```

2. Create Kubernetes secret to pull images from private container registry
```
kubectl create secret docker-registry regcred \
    --namespace=threatoptix \
    --docker-server=orcasecurity.jfrog.io \
    --docker-username=orca-threatoptix-ro \
    --docker-password=<paste token provided by Orca>
```

3. Add Orca Helm Chart repo
```
helm repo add orca-to-helm-charts https://orcasecurity.github.io/orca-to-helm-charts
```

4. Install TO monitor
```
helm install to-monitor orca-to-helm-charts/to-monitor \
    --namespace threatoptix \
    --set toConfig=<paste base64 encoded config string provided by Orca>
```
