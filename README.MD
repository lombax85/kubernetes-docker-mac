# Kubernetes example on local Docker for Mac

## Quickstart:

---
#### OPTIONAL: build your own images:

- Create an account on Docker hub and create a new project
- Go into `./docker-compose/docker-compose.yml` file and change the following image names and tags according to the 
new project you created on the Docker Hub

```
lombax85/kubetestphp:0.1
lombax85/kubetestmysql:0.1
```
----

- Enable Kubernetes in Docker for Mac Preferences
- Login to docker hub, build and push the images

```
cd docker-compose  
docker login
docker-compose build
docker-compose push
```

- Deploy the stack

```
docker stack deploy -c docker-compose.yml kubetest
```

- Wait for the stack to be running  

- Connect to http://localhost - the php container will connect to mysql container
If you see a connection error, wait for the MySQL Container to be up and running

----
Some commands to inspect the stack:

```
docker stack ls
docker stack services kubetest
kubectl get all --all-namespaces

```

Remove the stack

```
docker stack rm kubetest
```