# Aizen remote package

A Helm chart for training Aizen models on remote GPU machines

## Prerequisites
- Kubernetes 1.25+
- Helm 3.2.0+
- Persistent Volume(PV) provisioner support in the underlying infrastructure
- Object Store 

## Get Helm Repository Info
```
helm repo add aizenremote https://aizen-corp.github.io/helm-charts/aizenremote
helm repo update
```
## Install Aizen remote components using chart properties
```
helm install [RELEASE_NAME] aizenremote/aizenremote
```
