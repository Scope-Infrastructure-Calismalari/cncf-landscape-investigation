# Orchestration & Management

 This section covers everything from Kubernetes itself, one of the key enablers of cloud native development to the infrastructure layers responsible for inter app, and external communication. Inherently scalable, cloud native apps rely on automation and resilience, enabled by these tools.

##  Scheduling & Orchestration

Orchestration and scheduling refer to running and managing containers across a cluster. A cluster is a group of machines, physical or virtual, connected over a network (see cloud native networking).

Tools of this category allow engineers to build computing environments without human intervention.

* Kubernetes
* Volcano
* Crossplane 
* Docker Swarm
* Amazon Elastic Container Service (ECS)
* Karmada
* kube-rs


## Coordination & Service Discovery

Modern applications are composed of multiple individual services that need to collaborate to provide value to the end user. To collaborate, they communicate over a network (see cloud native networking), and to communicate, they must first locate one another. Service discovery is the process of figuring out how to do that.

* CoreDNS
* etcd
* Apache Zookeeper
* Netflix EurekaKraken
* Nacos

## Remote Procedure Call  

Remote Procedure Call (RPC) is a particular technique enabling applications to talk to each other. It's one way of structuring app communication.

* gRPC
* Apache Thrift
* Dubbo
* go-zero
* kratos

## Service Proxy  

A service proxy is a tool that intercepts traffic to or from a given service, applies some logic to it, then forwards that traffic to another service. It essentially acts as a “go-between” that can collect information about network traffic as well as apply rules to it. This can be as simple as serving as a load balancer that forwards traffic to individual applications or as complex as an interconnected mesh of proxies running side by side with individual containerized applications handling all network connections.

While a service proxy is useful in and of itself, especially when driving traffic from the broader network into a Kubernetes cluster, service proxies are also building blocks for other systems, such as API gateways or service meshes, which we'll discuss below.

* Envoy
* Contour
* MetalLB
* Traefik
* HAProxy
* Caddy
* NGINX
* Netflix Zuul
* Tengine

## API Gateway 

While humans generally interact with computer programs via a GUI (graphical user interface) such as a web page or a desktop application, computers interact with each other through APIs (application programming interfaces). But an API shouldn't be confused with an API gateway.

An API gateway allows organizations to move key functions, such as authorizing or limiting the number of requests between applications, to a centrally managed location. It also functions as a common interface to (often external) API consumers.

* Emissary-Ingress
* Kong
* Sentinel
* Gloo
* Gravitee.io
* APISIX
* Easegress


## Service Mesh

Service meshes manage traffic (i.e. communication) between services. They enable platform teams to add reliability, observability, and security features uniformly across all services running within a cluster without requiring any code changes.

Along with Kubernetes, service meshes have become some of the most critical infrastructure components of the cloud native stack.

* Linkerd
* Istio
* Consul
* Meshery
* Open Service Mesh



As we've seen, tools in this layer deal with how all these independent containerized services are managed as a group. Orchestration and scheduling tools can be thought of as a cluster OS managing containerized applications across your cluster. Coordination and service discovery, service proxies, and service meshes ensure services can find each other and communicate effectively in order to collaborate as one cohesive app. API gateways are an additional layer providing even more control over service communication, in particular between external applications. Next, we'll discuss the application definition and development layer — the last layer of the CNCF landscape. It covers databases, streaming and messaging, application definition, and image build, as well as continuous integration and delivery.
