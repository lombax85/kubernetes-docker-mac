## Kubernetes on local Docker for Mac

### Quickstart:

Enable Kubernetes in Docker Preferences

Login to docker hub, build and push the images

```
cd docker-compose  
docker login
docker-compose build
docker-compose push
```

Deploy the stack

```
docker stack deploy -c docker-compose.yml kubetest
```

Wait for the stack to be running  

Connect to http://localhost - the php container will connect to mysql container
If you see a connection error, wait for the MySQL Container to be up and running

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