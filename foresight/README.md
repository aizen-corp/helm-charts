# Aizen Foresight (foresight) package

A Helm chart for Aizen foresight platform for machine learning pipelines

## Prerequisites
- Kubernetes 1.25+
- Helm 3.2.0+
- Persistent Volume(PV) provisioner support in the underlying infrastructure
- Object Store 

## Get Helm Repository Info
```
helm repo add aizen-foresight https://aizen-corp.github.io/helm-charts/foresight
helm repo update
```
## Installing foresight chart
```
helm install [RELEASE_NAME] aizen-foresight/foresight
```
## Values

### foresight

| Key | Type | Default | Description |
|-----| -----| ------- | ----------- |
| global.image_registry | string | aizen.repo.com | The docker image registry to use |
| global.image_tag | string | 0.0.1 | Default tag for the image |
| global.image_secret | string | "" | Secret to access docker image registry |
| global.image_pullpolicy | string | Always | Image pull policy |
| global.storage_class | string | standard | Backend storage |
| global.clustername | string | "" | Required name used to create unique buckets for backend object store |j
| global.cloud_provider_type | string | minio | Cloud provider type |
| global.cloud_provider_region | string | us-west-1 | Cloud provider region name |
| global.customer_bucket_name | string | aizencorp-bucket/foresight | Customer bucket name |
| global.storage_type | string | local | Default storage type |
| global.s3.endpoint_url | string | "" |S3 endpoint url |
| global.s3.secrets.enabled | boolean | false | Enable s3 access |
| global.s3.secrets.values.s3_access_key | string | "" | Define s3 access key |
| global.s3.secrets.values.s3_secret_key | string | "" | Define s3 secret key |
| global.ingress.enabled | boolean | false | Enable ingress |
| global.ingress.host | string | "" | Specify ingress ip address |
