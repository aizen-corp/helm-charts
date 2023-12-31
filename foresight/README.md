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

### Aizen Foresight core component deployment

| Key | Type | Default | Description |
|-----| -----| ------- | ----------- |
| foresight-core.enabled | string | false | Set this to "true" to deploy aizen foresight core components |
| global.image_registry | string | aizen.repo.com | The docker image registry to use |
| global.image_tag | string | "" | common tag for all container images |
| global.image_secret | string | "" | Secret to access docker image registry |
| global.image_pullpolicy | string | IfNotPresent | Image pull policy |
| global.storage_class | string | standard | Backend storage |
| global.clustername | string | mycluster | Name used to create unique buckets for backend object store |
| global.cloud_provider_type | string |"" | Cloud provider type |
| global.cloud_provider_region | string | "" | Cloud provider region name |
| global.customer_bucket_name | string | "" | Customer bucket name |
| global.storage_type | string | local | Default storage type |
| global.s3.endpoint_url | string | "" |S3 endpoint url for cloud provider |
| global.s3.secrets.enabled | boolean | false | Enable s3 access |
| global.s3.secrets.values.s3_access_key | string | "" | Define s3 access key |
| global.s3.secrets.values.s3_secret_key | string | "" | Define s3 secret key |
| global.ingress.enabled | boolean | false | Enable ingress |
| global.ingress.host | string | "" | Specify ingress ip address |
| global.log.enabled | boolean | false | Enable logging |
| global.log.volume_size | string | 50Gi | Volume size for storing log files |
| global.mlflow.mysql.primary.persistence.storageClass | string | standard | Default storage class |
| global.mlflow.mysql.primary.persistence.size | string | 8Gi | Default size for mlflow mysql pvc |
| global.mlflow.artifact.secrets.values.mlflow_artifacts_destination | string | s3://foresight-mlflow | Default s3 destination |
| global.mlflow.artifact.secrets.values.mlflow_access_key_id | string | "" | Define s3 access key |
| global.mlflow.artifact.secrets.values.mlflow_access_secret_key | string | "" | Define s3 secret key |
| global.mlflow.artifact.secrets.values.mlflow_endpoint_url | string | ""  | Define s3 end point url for mlflow |
| global.mlflow.artifact.region | string | "" | Define s3 region name |
| foresight-core.foresight-storage.blkcache_size_mb | int | 2048 | Block cache size |
| foresight-core.foresight-storage.memtable_size_mb | int | 1024 | Mem table size |
| foresight-core.foresight-storage.resources.limits.cpu | string | 8 | cpu limit |
| foresight-core.foresight-storage.resources.limits.memory | string | 16Gi | memory limit |
| foresight-core.foresight-storage.resources.requests.cpu | string | 2 | requested cpu from the cpu limit |
| foresight-core.foresight-storage.resources.requests.memory | string | 2Gi | requested memory from the memory limit |

### Aizen Foresight infra component deployment (pre-requistes)
