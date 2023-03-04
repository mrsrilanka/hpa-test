# hpa-test
This repo contains horizontal pod autoscaling demo content

Official kubernetes documentation link  https://kubernetes.io/docs/tasks/run-application/horizontal-pod-autoscale/

Metrics server https://github.com/kubernetes-sigs/metrics-server 

## Solving resource constraints in Kubernetes

### Background of the issue

* Dev Teams are deploying to Kubernetes clusters with resources defined with requests and
limits with number of replicas.

* But most of the time teams overprovisions the resources in their deployments/sts.

* As a SRE/K8S engineer you must expand the on-premises clusters to meet the demand. If it’s a Kubernetes cluster in the cloud, then something like Azure Cluster Autoscaler will occur.

* Both scenarios are highly inefficient and less cost effective.

## Horizontal Pod Autoscaling

So how can we address this issue?

One way to address this is to use Horizontal Pod Autoscaling (HPA)

### What is HPA?

When you have HPA implemented in your deployment namespace in your Kubernetes clusters you can,

Improve resource utilization

Increase availability

Improve performance

Reduce operational overhead

Improve cost efficiency

What do you need to deploy HPA?

#

A Kubernetes cluster with admin privileges

A Metric Server

A Deployment
