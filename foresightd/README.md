# Aizen Foresight Desktop(foresightd) package

A Helm chart for foresightd platform for machine learning pipelines

## Prerequisites
- Kubernetes 1.25+
- Helm 3.2.0+
- Persistent Volume(PV) provisioner support in the underlying infrastructure

## Get Helm Repository Info
```
helm repo add aizen-foresightd https://aizen-corp.github.io/helm-charts/foresightd
helm repo update
```
## Installing foresightd chart
```
helm install [RELEASE_NAME] aizen-foresightd/foresightd
```
## Values

### foresightd

| Key | Type | Default | Description |
|-----| -----| ------- | ----------- |
| global.image_registry | string | aizen.repo.com | The docker image registry to use |
| global.image_tag | string | 0.0.1 | Default tag for the image |
| global.storage_class | string | standard | Backend storage |
| global.image_secret | string | "" | Secret to access docker image registry |
| global.fileshare | string | "" | Local fileshare mount if any exists |
| foresightd-core.image_tag | string | 0.0.1 | Image tag for core docker image |
| foresightd-core.volume_size | string | 5Gi | Volume size for core |
| foresightd-core.resources.limits.cpu | string | 1 | Max cpu |
| foresightd-core.resources.limits.memory | string | 4Gi | Max memory |
| foresightd-console.image_tag | string | 0.0.1 | Image tag for console docker image |
| foresightd-console.volume_size | string | 5Gi | Volume size for console |
| foresightd-console.resources.limits.cpu | string | 1 | Max cpu |
| foresightd-console.resources.limits.memory | string | 4Gi | Max memory |
| foresightd-mlearn.image_tag | string | 0.0.1 | Image tag for mlearn docker |
| foresightd-mlearn.volume_size | string | 5Gi | Volume size for mlearn |
| foresightd-mlearn.mysql.primary.persistence.storageClass | string | standard | Backend storage |
| foresightd-mlearn.mysql.primary.persistence.size | string | 8Gi | Volume size |
| foresightd-mlearn.mysql.auth.password | string | "" | mysql password for root user |
| foresightd-mlearn.mlflow.image_tag | string | 0.0.1 | Image tag for mlflow docker image |
| foresightd-mlearn.mlflow.resources.limits.cpu | string | 200m | Max cpu |
| foresightd-mlearn.mlflow.resources.limits.memory | string | 2Gi | Max memory |
| foresightd-mlearn.resources.limits.cpu | string | 2 | Max cpu |
| foresightd-mlearn.resources.limits.memory | string | 4Gi | Max memory |

