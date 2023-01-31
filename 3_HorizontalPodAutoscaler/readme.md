```
k apply -f application.yaml
k apply -f hpa.yaml
kubectl -n hpa-test run -i --tty load-generator --rm --image=busybox --restart=Never -- /bin/sh -c "while sleep 0.01; do wget -q -O- http://php-apache; done"

kubectl get deploy -n hpa-test


kubectl delete ns hpa-test --cascade
```