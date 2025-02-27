# kubernates

## OBJECTS

### POD :
A Pod is the basic execution unit in Kubernetes, consisting of:

1. One or more containers (e.g., Docker containers)
2. Shared storage/volumes for containers to access
3. Shared networking with unique IP address
4. Specifications for containers' runtime environment

Characteristics of Pods:

1. Ephemeral: Pods are temporary and can be deleted/recreated
2. Collocated: Containers in Pod run on same node/host
3. Shared context: Containers share same network, storage, and runtime environment
4. Managed by Kubernetes: Pods are created, scheduled, and managed by Kubernetes

Pod Components:

1. Containers: One or more containers (e.g., Docker)
2. Volumes: Shared storage for containers
3. Init Containers: Special containers running before main containers
4. Pod Specifications: Metadata defining Pod characteristics

Pod Lifecycle:

1. Pending: Pod scheduled but not running
2. Running: Pod active and containers running
3. Succeeded: Pod completed successfully
4. Failed: Pod failed or terminated abnormally

### SERVICE :

### VOLUME :

### NAMESPACE :

### REPLICASET :

### DEPLOYMENT :

### STATEFULSET :

### DAEMONSET :

### JOB :


## Commands

kubectl apply -f pod.yaml

kubectl get pods

kubectl get pods -o wide

kubectl delete -f pod.yaml

kubectl get pods podname -o wide

kubectl log -f podname || 2container pod kubectl log -f podName -c containerName 

kubectl exec podname -- uptime 

kubectl exec testpod -c c01 -- uptime  -->  
14:03:50 up  5:36,  0 user,  load average: 1.32, 1.06, 0.90


kubectl exec -it podname -- /bin/bash || kubectl exec -it podname -c c01 -- /bin/bash

kubectl get pods --show-labels

kubectl get pods -l key=value || kubectl get pods -l key!=value

kubectl label pods podname key=value

kubectl label node podname key=value

kubectl get pods -l 'key in (value1, value2)'

kubectl get pods -l 'key notin (value1, value2)'

kubectl delete pods -l 'key notin (value1, value2)'

kubectl get rs

kubectl describe rs nameRs

kubectl delete rs nameRs

kubectl get deploy

kubectl describe deploy mydeploy

kubectl rollout status deploy/mydeploy

kubectl rollout history deploy/mydeploy

kubectl rollout undo deploy/mydeploy --to-revision=1|2|3...

kubectl delete deploy mydeploy






