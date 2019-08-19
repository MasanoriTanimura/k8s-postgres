# k8s-postgres

## 構築手順

```
$ git clone https://github.com/MasanoriTanimura/k8s-postgres.git
$ cd k8s-postgres
$ kubectl create -f postgres-configmap.yaml
configmap "postgres-config" created
$ kubectl create -f postgres-storage.yaml
persistentvolume "postgres-pv-volume" created
persistentvolumeclaim "postgres-pv-claim" created
$ kubectl create -f postgres-service.yaml
service "postgres" created
$ minikube service postgres --url  | sed 's,.*/,,'
192.168.xx.xxx:yyyyy
$ psql -h 192.168.xx.xxx -U postgresadmin --password -p yyyyy postgresdb
```
