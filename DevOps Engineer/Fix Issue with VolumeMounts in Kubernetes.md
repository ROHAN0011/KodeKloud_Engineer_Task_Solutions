Checking the configmap to know the url and port, and page location
```
kubectl get cm
```
Exporting the pod yaml
```
kubectl get pod nginx-phpfpm -o yaml  > /tmp/nginx.yaml
```
Now open the vi editor and edit the nginx.yaml. Replace all /usr/share/nginx/html to /var/www/html
