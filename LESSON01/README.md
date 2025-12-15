# Kubernetes 101

[Kubernetes 101 Course - FREE](https://community.kubeskills.com/c/101-course)

## Lesson 00 - The What and How of Kubernetes

- Start with concrete example in killercoda.com
- use drawing pad
- cover smallest unit (pods)
- cover largest unit (deployments)
- 

### Docker and K8s Differences

```bash
# run a container in docker
docker run -d --name docker-success -p 80:80 chadmcrowell/docker-success:v1

# show running container
docker ps

# pull up webpage on port 80

# run a container in kubernetes
k create deploy k8s-success --image chadmcrowell/k8s-success:v1; k expose deploy k8s-success --port 80 --type NodePort

# get nodeport
k get svc

# pull up webpage on nodeport (e.g. 30000)

# to show port is already taken, start another docker container
docker run -d --name another-container -p 80:80 chadmcrowell/docker-success:v1

# create another pod with success
k create deploy k8s-success3 --image nginx; k expose deploy k8s-success3 --port 80 --type NodePort

```

This will be able to act as it's own host, so, you can have port 80 exposed on each pod, and that removes that limitation you had with Docker. Also, because it's not coupled with any host, it can move around to any infrastructure you want.