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

Replicas (blueprints)
= Deployment (use to replicate)

StatefulSet
= for DB containers

Worker Nodes:
Container Runtime
Kubelet [take config, start the pod, assign resources]
Kube Proxy (Forwarding requests)

Master Nodes: [control cluster nodes]
API Server [cluster gateway, queries, gate-keeper (auth)]
Scheduler [start the pod in worker nodes]
Controller Manager [monitor the pods, detect state changes]
 = CM to S to Kubelet
etcd [key value store, cluster brain, cluster changes]

