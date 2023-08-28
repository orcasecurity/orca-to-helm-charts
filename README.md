# Installation

1. Add Orca Helm Chart repo
```
helm repo add orca-to-helm-charts https://orcasecurity.github.io/orca-to-helm-charts
```

2. Install TO monitor
```
helm upgrade --install to-monitor orca-to-helm-charts/to-monitor \
    --namespace threatoptix \
    --create-namespace \
    --set toConfig=<paste base64 encoded config string provided by Orca> \
    --set image.registry.password=<paste token provided by Orca>
```
