[Login to given app server as per task then switch to root]

Checking existing network on server
```
docker network ls
```
Creating docker network as per given task Driver,Subnet,IPrange,Network Name [Change this as per your task]
```
docker network create -d macvlan --subnet=172.168.0.0/24 --ip-range=172.168.0.2/24 ecommerce
```
Checking updated docker network
```
docker network ls
```
Final Validation
```
docker network inspect ecommerce
```
