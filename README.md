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






