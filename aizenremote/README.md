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

### Chart properties
| Key | Type | Default | Description |
|-----|------|---------|-------------|
| global.clustername | string | myremotecluster | Unique cluster name |
| global.s3.endpoint_url | string | "" | S3  endpoint URL for cloud provider |
| global.s3.secrets.values.s3_access_key | string | "" | Define an s3 access key |
| global.s3.secrets.values.s3_secret_key | string | "" | Define an S3 secret key |
| global.customer_bucket_name | string | "" | customer s3 bucket name |
| global.storage_class | string | standard | Backend storage |
| global.cloud_provider_type | string | "" | Cloud provider type |
| global.cloud_provider_region | string | "" | Cloud provider region name |
| global.image_registry | string | aizen.repo.com | The docker image registry to use |
| global.image_tag | string | "" | common tag for all container images |
| global.image_secret | string | "" | Secret to access docker image registry |
| metastorage.volume_size | string | 100Gi | Volume size for metastorage files |


