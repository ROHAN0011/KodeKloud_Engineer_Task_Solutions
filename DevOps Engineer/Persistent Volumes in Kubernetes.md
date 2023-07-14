[Run below commands on jump-host server]
```
vi /tmp/pvc.yaml
```
In Vi editor paste below script (check & do changes some requied places as per your task like names, storage, path etc.)
```
---
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-datacenter
spec:
  capacity:
    storage: 3Gi
  accessModes:
    - ReadWriteOnce
  storageClassName: manual
  hostPath:
    path: /mnt/security
---
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-datacenter
spec:
  accessModes:
    - ReadWriteOnce
  storageClassName: manual
  resources:
    requests:
      storage: 2Gi
---
apiVersion: v1
kind: Pod
metadata:
  name: pod-datacenter
  labels:
    app: web
spec:
  containers:
    - name: container-datacenter
      image: httpd:latest
      volumeMounts:
      - mountPath: "/usr/share/httpd/html"
        name: storage-nautilus
      ports:
        - containerPort: 80
  volumes:
    - name: storage-nautilus
      persistentVolumeClaim:
        claimName: pvc-datacenter
		

---
apiVersion: v1
kind: Service
metadata:
  name: web-datacenter
spec:
  type: NodePort
  selector:
    app: web
  ports:
    - port: 80
      targetPort: 80
      nodePort: 30008
```
Then,
```
kubectl create -f /tmp/pvc.yaml
```
