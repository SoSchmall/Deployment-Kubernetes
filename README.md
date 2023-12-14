# Deploy on Kubernetes

## Introduction
This project contains three microservices:
    * A service for FastApi application.
    * A PostgresSQL database.
    * PGAdmin, an administration interface for managing the databases.

The primary goal of this project is to deploy the application using three different methods:
    * Deploying in a standard way.
    * Deploying with Helm.
    * Deploying with Kustomize.


There are three repositories for deploying these services:

    * YAML-STANDARD
    * HELM
    * kustomize


## YAML-STANDARD

* Create namespace standard
```sh
kubectl create namespace standard
```
* Apply the kubernetes manifests
```sh
kubectl apply -f . -n standard
```
## HELM:

_The following commands to deploy with helm:_ 

* Install:
```sh
helm install my-app --namespace helm ./HELM
```
* Uninstall:
```sh
helm uninstall my-app -n helm
```

## kustomize:

_If we want to build resources on dev namespace for example:_

* Create namespace dev
```sh
kubectl create namespace dev
```

* Build with kustomize on dev namespace
```sh
kustomize build overlays/dev | kubectl apply -f -
```

* Delete everything on namespace dev
```sh
kustomize build overlays/dev | kubectl delete -f -
```
* Delete namespace dev
```sh
kubectl delete namespace dev
```