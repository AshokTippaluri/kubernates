# kubernates

## OBJECTS

### POD :

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


