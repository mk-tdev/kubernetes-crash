https://www.youtube.com/watch?v=X48VuDVv0do&t=4434s

Pod:
Small unit of K8s

[Node => [Pod (Containers)]] 
= Pods gets IP (user for communication)
= Service (permanent IP) comes in to avoid keep changing the IP of PODS (when dies)
= External Service (Website for ex) | Internal Service (DB for ex)
  > Ingress (Forwarding to Service)
= ConfigMap
  > external configuration
= Secret
  > credentials in base64 encoded
= Volumes [data storage]
================================================================================================================
Replicas (blueprints)
= Deployment (use to replicate)

StatefulSet
= for DB containers
================================================================================================================
Worker Nodes:
Container Runtime
Kubelet [take config, start the pod, assign resources]
Kube Proxy (Forwarding requests)
================================================================================================================
Master Nodes: [control cluster nodes]
API Server [cluster gateway, queries, gate-keeper (auth)]
Scheduler [start the pod in worker nodes]
Controller Manager [monitor the pods, detect state changes]
 = CM to S to Kubelet
etcd [key value store, cluster brain, cluster changes]
================================================================================================================
Minikube and Kubectl:

Minikube - [open source for local dev]
 - refer pictures

Kubectl [CLI for kubernets cluster]
 - to create pods and others
 - also used for cloud cluster

Installation:
 brew update
 brew install hyperkit
 brew install minikube [as dep kubernetes-cli]

Commands
 kubectl | minikube

 minikube start --vm-driver=hyperkit
 kubectl get nodes
 minikube status
 kubectl version

Basic kubectl Commands
 kubectl get nodes [get status]
 kubectl get pod
 kubectl get services
 kubectl create deployment nginx-depl --image=nginx [Deployment creates the pods]
 kubectl get deployment [managed by kubernets for everything under]
 kubectl get replicaset
 kubectl edit deployment nginx-depl
 kubectl create deployment mongo-depl --image=mongo
 kubectl describe pod
 kubectl logs mongo-depl-79585f75cf-s44rf
 kubectl exec -it mongo-depl-79585f75cf-s44rf -- bin/bash [interactive terminal]
 kubectl delete deployment mongo-depl
 kubectl apply -f config-file.yaml  [later]

================================================================================================================

Configuration file:

metadata
spec
status [auto]

kubectl get service
kubectl describe service nginx-service
kubectl get pod -o wide
kubectl get deployment nginx-deployment -o yaml 
kubectl get deployment nginx-deployment -o yaml > nginx-deployment-result.yaml
kubectl delete -f nginx-service.yaml 
kubectl delete -f nginx-deployment.yaml
kubectl delete deployment nginx-depl
kubectl delete deployment --all