# Deploying Dagster on Helm

## Commands

### Install kubernetes to a specific version

```shell
$ minikube start --kubernetes-version=v1.19.15
```

### Install helm to a specific version

[Helm 3.4.2](https://github.com/helm/helm/releases?q=helm+3.4.2&expanded=true)

[Installing Helm - From the Binary Releases](https://helm.sh/docs/intro/install/)

1. Download your desired version
2. Unpack it (tar -zxvf helm-v3.0.0-linux-amd64.tar.gz)
3. Find the helm binary in the unpacked directory, and move it to its desired destination

```shell
$ mv linux-amd64/helm /usr/local/bin/helm
```

### Add the Dagster Helm chart repository

```shell
$ helm repo add dagster https://dagster-io.github.io/helm
$ helm show values dagster/dagster > values.yaml
$ helm upgrade --install dagster dagster/dagster -f values.yaml
```

### You can access Dagit by running the following commands

```shell
$ helm repo add dagster https://dagster-io.github.io/helm
$ helm show values dagster/dagster > values.yaml
$ helm upgrade --install dagster dagster/dagster -f values.yaml
```

### Deleting a Helm chart

```shell
$ helm delete dagster
```
