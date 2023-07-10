Checking the configmap to know the url and port, and page location
```
kubectl get cm
```
Exporting the pod yaml
```
kubectl get pod nginx-phpfpm -o yaml  > /tmp/nginx.yaml
```
Now open the vi editor and edit the nginx.yaml (Replace all /usr/share/nginx/html to /var/www/html)
```
vi /tmp/nginx.yaml
```
Then, Force apply or replace the yaml
```
kubectl replace -f /tmp/nginx.yaml --force
```
Copy the index.php to /var/www/html folder of container as per given task
```
kubectl cp  /home/thor/index.php  nginx-phpfpm:/var/www/html -c nginx-container
```
Final Validation
