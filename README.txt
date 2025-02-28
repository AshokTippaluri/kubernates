kubernates

OBJECTS -
1. Pod: Basic execution unit, 1+ containers, shared resources
2. Node: Single worker machine in Kubernetes cluster, hosts Pods
3. Namespace: Virtual cluster within physical cluster, isolates resources
4. Deployment: Manages Pod creation, scaling, updates, and deletion
5. ReplicaSet: Ensures specified number of identical Pods running
6. StatefulSet: Manages stateful applications, persistent storage
7. DaemonSet: Runs one Pod per Node, typically for monitoring/logging
8. Job: Creates Pods for batch jobs, ensures completion
9. CronJob: Schedules Jobs to run at specific times/intervals
10. Service: Abstracts access to Pods, provides network identity
11. Ingress: Manages external access to Services, routes traffic
12. ConfigMap: Stores configuration data for Pods and containers
13. Secret: Stores sensitive data (e.g., passwords, keys) securely
14. PersistentVolume (PV): Network storage resource for Pods
15. PersistentVolumeClaim (PVC): Request for PV storage by Pods
16. Role: Defines permissions for resources within Namespace
17. RoleBinding: Grants permissions defined by Role to users/groups

POD :
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

1. Pending: The pod has been accepted by kubernates syatem, but not running or if the pod can not sechudle because of resources constrains.
2. ContainerCreating - Container has been bounded to the node or one or more container image is still downloading or one or more container is still creating.
3. Running: Pod active and containers running
4. Succeeded: Pod completed successfully
5. Failed: Pod failed or terminated abnormally or container exited non zero status or was turminated by system.
6. Unknown: state of the pod could not uptained or network errors like communication to hosts
7. Terminating: The pod as been terminated by api call.

 SERVICE :

 VOLUME :

 NAMESPACE :

 REPLICASET :

 DEPLOYMENT :

 STATEFULSET :

 DAEMONSET :

 JOB :


 Commands

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
kubectl delete pvc -l app=nginx
kubectl delete deploy mydeploy


Troubleshoot:
kubectl get pod podname
kubectl describe pod podname
kubectl logs -f podname
kubectl exec podname -it -- /bin/bash

sts
kubectl exec nginx-statefulset-0 -- curl nginx-statefulset-1(podname).nginx-headless(servicename)
kubectl exec nginx-statefulset-1 -- sh -c 'echo nginx-statefulset-0 > /usr/share/nginx/html/nginx.html'




