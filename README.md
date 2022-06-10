# k8s-tekton-demo

This repository has been created to with the sole purpose of demo-ing [Tekton](https://tekton.dev)

This repository has three branches

- master

    * Files required to build Tekton Pipeline(s) on top of a Kubernetes cluster created using [k3d](https://github.com/rancher/k3d)

- docker

    * `Dockerfile` to build an Alpine based image with `terraform`

- terraform

    * A super basic `terraform` code

**NOTE**: In production or real life scenarios, please break these into individual repositories with a _good_ branching strategy. I will leave it up to you or your organization's practices to decide what _good_ looks like. :)

# Install k3s
```
export INSTALL_K3S_VERSION="v1.21.5+k3s2"
curl -sfL https://get.k3s.io | sh -s - --write-kubeconfig-mode 777 --docker
```

# more details
[install k3s](https://github.com/amitkarpe/setup/blob/main/k3s.sh)

# Tekton install

```
kubectl create ns tekton-pipelines
kubectl apply -f https://storage.googleapis.com/tekton-releases/pipeline/previous/v0.24.0/release.yaml
kubectl apply -f https://github.com/tektoncd/dashboard/releases/download/v0.26.0/tekton-dashboard-release.yaml


kubectl apply -f https://storage.googleapis.com/tekton-releases/triggers/previous/v0.20.0/release.yaml
kubectl apply -f https://storage.googleapis.com/tekton-releases/triggers/previous/v0.20.0/interceptors.yaml
```