[Run following commands on jump_host server]

kubectl create namespace <paste_given_namespace>

vi /tmp/time.yaml


kubectl create -f /tmp/time.yaml

kubectl get pods -n <paste_given_namespace>
