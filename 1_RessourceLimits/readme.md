##Example 1

###Limits & Requests
```
k apply -f 1_limits.yaml
```

Pod is created with Request and Limits

##Example 2

###Ressource Quotas
```
k apply -f 2_resource_quota.yaml

kubectl run pod1 --image=nginx
kubectl run pod2 --image=nginx
kubectl run pod3 --image=nginx
```

Error from server (Forbidden): pods "pod3" is forbidden: exceeded quota: pod-demo, requested: pods=1, used: pods=2, limited: pods=2

##Example 3

###Range Limit
```
k apply -f 3_limit_range.yaml

k apply -f 3_limit_range_pod.yaml
```

Error from server (Forbidden): error when creating "STDIN": pods "memory-demo-pod" is forbidden: [minimum memory usage per Container is 500Mi, but request is 100Mi, maximum memory usage per Container is 1Gi, but limit is 1536Mi]


##Example 4

###Priority
```
k apply -f 4_pod_priority.yaml

k apply -f 4_pod_priority_pods.yaml
```

Error from server (Forbidden): error when creating "STDIN": pods "memory-demo-pod" is forbidden: [minimum memory usage per Container is 500Mi, but request is 100Mi, maximum memory usage per Container is 1Gi, but limit is 1536Mi]

