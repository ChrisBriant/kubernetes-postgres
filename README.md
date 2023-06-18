# Kubernetes Deployments for Postgres with PGAdmin

## About

Just playing around with Kubernetes, spins up some containers, including Postgres so I can play around with the storage and accessing the DB using pgadmin and from other containers.


## Minikube commands
minikube ssh
kubectl exec -it postgres-deployment-59f7b8b68f-9ggf8 -c postgres -- /bin/bash
### Delete the minikube vm
minikube delete
### Start and stop
minikube start
minikube stop


## Create ubuntu container and access the terminal
kubectl run ubuntu --image=ubuntu:latest --command -- sleep 3000
kubectl exec --tty --stdin ubuntu -- bash
## On Ubuntu Container
apt-get update
apt-get install net-tools
ifconfig
### Ping the postgres container
apt-get install iputils-ping
ping 10.244.0.3
### Connect to the database
psql -h 10.244.0.3 -U postgres -d postgres

## Create a container with an environment variable set inside
kubectl run ubuntu2 --env="MY_ENV=hello" --image=ubuntu:latest --command -- sleep 3000


