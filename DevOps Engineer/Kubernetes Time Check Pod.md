[Run following commands on jump_host server]
```
kubectl create namespace <paste_given_namespace>
```
```
vi /tmp/time.yaml
```
In below script just change the namespace, TIME_FREQ, image, mountpath of volumeMounts and args: given full path etc. as per your task
```
apiVersion: v1
kind: ConfigMap
metadata:
  name: time-config
  namespace: devops
data:
  TIME_FREQ: "2"
---
apiVersion: v1
kind: Pod
metadata:
  name: time-check
  namespace: devops
  labels:
    app: time-check
spec:
  volumes:
    - name: log-volume
      emptyDir: {}
  containers:
    - name: time-check
      image: busybox:latest
      volumeMounts:
        - mountPath: /opt/dbs/time
          name: log-volume
      envFrom:
        - configMapRef:
            name: time-config
      command: ["/bin/sh", "-c"]
      args:
        [
          "while true; do date; sleep $TIME_FREQ;done > /opt/dbs/time/time-check.log",
        ]
```
```
kubectl create -f /tmp/time.yaml
```
```
kubectl get pods -n <paste_given_namespace>
```
