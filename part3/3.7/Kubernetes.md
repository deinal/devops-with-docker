## Kubernetes

An open-source container-orchestration system for automating application deployment, scaling, and management.

Kubernetes is built in layers of abstraction. The base consist of a cluster physical or virtual machines with a shared network to communicate between each server. One of the servers (or a small group) functions as the master. The master server schedule work and orchestrate communication between the others as well as expose an API for users and clients. The other servers act as nodes and run workloads. Applications are run in containers - so each node need a container runtime (Docker). Users interact with the cluster by communicating with the main API server either directly or with clients and libraries. The final layer of the cluster is the user's declarative plan in the form of a JSON or YAML file. 

#### Master server
- etcd: lightweight, distributed key-value store that can be configured to span across multiple nodes
- API server: processes and validates REST requests and updates state of the API objects in etcd, allowing clients to configure workloads and containers across worker nodes
- Scheduler:  selects which node an unscheduled pod runs on based on resource availability
- Controller manager:  a process that manages a set of core Kubernetes controllers where a controller is a reconciliation loop that drives actual cluster state toward the desired cluster state

#### Node
- Kubelet: start, stop and maintain containers organized into pods
- Kube-proxy: network proxy and load balancer, routs traffic to the appropriate container based on IP and port number of the incoming request
- Pod: a group of one or more containers with a shared network (localhost) and storage

![Kubernetes Architecture](https://upload.wikimedia.org/wikipedia/commons/thumb/b/be/Kubernetes.png/640px-Kubernetes.png)
