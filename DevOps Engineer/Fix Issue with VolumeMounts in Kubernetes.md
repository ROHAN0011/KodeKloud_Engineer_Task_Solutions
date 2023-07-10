Checking the configmap to know the url and port, and page location
```
kubectl get cm
```
Exporting the pod yaml
```
kubectl get pod nginx-phpfpm -o yaml  > /tmp/nginx.yaml
```
