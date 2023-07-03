[Enter below commands on jump_host server]


Checking existing deployment and  pods running status
```
kubectl get namespace
```
```
kubectl get pods
```

Creating yml file
```
vi /etc/replica.yml
```
Paste below script inside vi editor (Change some things like replicas, names, ports etc. as per task)
```
apiVersion: v1
kind: ReplicationController
metadata:
  name: nginx-replicationcontroller
  labels:
    app: nginx_app
    type: front-end
spec:
  replicas: 3
  selector:
    app: nginx_app
  template:
    metadata:
      name: nginx_pod
      labels:
        app: nginx_app
        type: front-end
    spec:
      containers:
        - name: nginx-container
          image: nginx:latest
          ports:
            - containerPort: 80
```
