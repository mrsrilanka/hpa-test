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

HorizontalPodAutoscaler (HPA) automatically updates a workload resource (such as a Deployment or StatefulSet), with the aim of automatically scaling the workload to match demand in kubernetes. 

When you have HPA implemented in your deployment namespace in your Kubernetes clusters you can,

1. Improve resource utilization

2. Increase availability

3. Improve performance

4. Reduce operational overhead

5. Improve cost efficiency

### What do you need to deploy HPA?

1. A Kubernetes cluster with admin privileges

2. A Metric Server

3. A Deployment

## Demo 

1. Create the namespace 

```
kubcelt create ns autoscale-test
```

2. Create the metrics server if it is not present in the cluser 

   a. Find if it is installed 

```
kubectl get pods -n kube-system | grep metric
```
  
  b. If it is not present deploy it with the following command. This will create the metric-server deployment with correct roles and rolebindings

```
kubectl apply -f components.yaml
```

3. Create the PHP Apache deployment exposing it in port 80

```
kubectl apply -f apache-test.yaml
```

4. Verify your service and deployment 

```
kubectl get all -n autoscale-test
```

4. Deploy  

# Q&A
