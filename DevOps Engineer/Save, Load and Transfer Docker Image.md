Login to given app server then switch to root

```
docker images
```
NOTE: ecommerce:xfusion is given server name for my task check and change this thing as per your task in further commands 
```
docker save -o /tmp/ecommerce.tar ecommerce:xfusion
```
```
ll /tmp/
```
```
scp /tmp/ecommerce.tar banner@stapp03:/tmp
```
From existing app server login to app server which is given to copy .tar file then switch to root
```
cd /tmp
```
```
ll
```
```
systemctl start docker
```
```
systemctl status docker
```
```
docker load -i ecommerce.tar
```
```
docker images
```
