# Monitoring Windows Container 

This sample shows how to monitor Windows Containers on Nano Server 2016 (build 14393).

## Goal

Use Prometheus deployed on Kubernetes to scrape metrics from Sonar metric agent endpoint. In this example, Windows container is external to Kubernetes cluster and Prometheus deployed on it.

## Prerequesites

Complete [WebAPI](https://github.com/infragravity/sonar-docker/tree/master/samples/WebApi) sample.

## Setup

1. Modify IP address and port to reference Sonar endpoint for Prometheus ( including annotations).
1. Run below commands to create service with endpoint in K8S

```bash
kubectl create -f ExternalDockerSvc.yml
kubectl create -f ExternalDockerEndpoint.yml
```

## Cleanup

Run below command to remove service and endpoing from K8S:

```bash
kubectl delete service nano-metrics 
```