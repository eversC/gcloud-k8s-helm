# gcloud-k8s-helm

## intro

A pretty basic Docker image, `FROM google/cloud-sdk`, additionally with `kubectl` and `helm` installed. 

Helm has an additional [plugin](https://github.com/nouney/helm-gcs) installed; "helm-gcs" to allow for use of a private helm repo in GCS


## authing

There is no authing performed automatically in the image. This must be done via CLI where required.

[gcloud docker cred helper](https://cloud.google.com/container-registry/docs/advanced-authentication#gcloud_as_a_docker_credential_helper) has been installed for authing against GCR

## versioning

The versions/tags will match those of the base image, `google/cloud-sdk`, appended with the Helm version (so that users can match this with the version of Tiller they're running).

None of the gcloud components (including `kubectl`) are upgraded.

The `helm` and `helm-gcs` (plugin) versions are defined in `ENV` statements in the [Dockerfile](Dockerfile)
