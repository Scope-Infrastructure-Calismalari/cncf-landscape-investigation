# Orchestration & Management

 This section covers everything from Kubernetes itself, one of the key enablers of cloud native development to the infrastructure layers responsible for inter app, and external communication. Inherently scalable, cloud native apps rely on automation and resilience, enabled by these tools.

#  Scheduling & Orchestration

Orchestration and scheduling refer to running and managing containers across a cluster. A cluster is a group of machines, physical or virtual, connected over a network (see cloud native networking).

Tools of this category allow engineers to build computing environments without human intervention.

* Kubernetes
* Volcano
* Crossplane 
* Docker Swarm
* Amazon Elastic Container Service (ECS)
* Karmada
* kube-rs

## Kubernetes

Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications.


## Volcano

A cloud native system for high-performance workloads

Volcano is system for running high-performance workloads on Kubernetes. It features powerful batch scheduling capability that Kubernetes cannot provide but is commonly required by many classes of high-performance workloads, including:

    Machine learning/Deep learning
    Bioinformatics/Genomics
    Other big data applications

These types of applications typically run on generalized domain frameworks like TensorFlow, Spark, PyTorch, and MPI. Volcano is integrated with these frameworks to allow you to run your applications without adaptation efforts while enjoying remarkable batch scheduling.

## Crossplane 

Build control planes without needing to write code. Crossplane has a highly extensible backend that enables you to orchestrate applications and infrastructure no matter where they run, and a highly configurable frontend that lets you define the declarative API it offers.


# Coordination & Service Discovery

Modern applications are composed of multiple individual services that need to collaborate to provide value to the end user. To collaborate, they communicate over a network (see cloud native networking), and to communicate, they must first locate one another. Service discovery is the process of figuring out how to do that.

* CoreDNS
* etcd
* Apache Zookeeper
* Netflix EurekaKraken
* Nacos



## CoreDNS

CoreDNS is a DNS server. It is written in Go. It can be used in a multitude of environments because of its flexibility. CoreDNS is licensed under the Apache License Version 2, and completely open source.

## etcd

etcd is a distributed reliable key-value store for the most critical data of a distributed system, with a focus on being:

Simple: well-defined, user-facing API (gRPC)
Secure: automatic TLS with optional client cert authentication
Fast: benchmarked 10,000 writes/sec
Reliable: properly distributed using Raft
etcd is written in Go and uses the Raft consensus algorithm to manage a highly-available replicated log.

etcd is used in production by many companies, and the development team stands behind it in critical deployment scenarios, where etcd is frequently teamed with applications such as Kubernetes, locksmith, vulcand, Doorman, and many others. Reliability is further ensured by rigorous testing.


# Remote Procedure Call  

Remote Procedure Call (RPC) is a particular technique enabling applications to talk to each other. It's one way of structuring app communication.

* gRPC
* Apache Thrift
* Dubbo
* go-zero
* kratos

## gPRC

gRPC is a modern open source high performance Remote Procedure Call (RPC) framework that can run in any environment. It can efficiently connect services in and across data centers with pluggable support for load balancing, tracing, health checking and authentication. It is also applicable in last mile of distributed computing to connect devices, mobile applications and browsers to backend services.

# Service Proxy  

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

## Contour

Contour is an open source Kubernetes ingress controller providing the control plane for the Envoy edge and service proxy.​ Contour supports dynamic configuration updates and multi-team ingress delegation out of the box while maintaining a lightweight profile.

## Envoy

As on the ground microservice practitioners quickly realize, the majority of operational problems that arise when moving to a distributed architecture are ultimately grounded in two areas: networking and observability. It is simply an orders of magnitude larger problem to network and debug a set of intertwined distributed services versus a single monolithic application.

Originally built at Lyft, Envoy is a high performance C++ distributed proxy designed for single services and applications, as well as a communication bus and “universal data plane” designed for large microservice “service mesh” architectures. Built on the learnings of solutions such as NGINX, HAProxy, hardware load balancers, and cloud load balancers, Envoy runs alongside every application and abstracts the network by providing common features in a platform-agnostic manner. When all service traffic in an infrastructure flows via an Envoy mesh, it becomes easy to visualize problem areas via consistent observability, tune overall performance, and add substrate features in a single place.

## MetalLB

Kubernetes does not offer an implementation of network load balancers (Services of type LoadBalancer) for bare-metal clusters. The implementations of network load balancers that Kubernetes does ship with are all glue code that calls out to various IaaS platforms (GCP, AWS, Azure…). If you’re not running on a supported IaaS platform (GCP, AWS, Azure…), LoadBalancers will remain in the “pending” state indefinitely when created.

Bare-metal cluster operators are left with two lesser tools to bring user traffic into their clusters, “NodePort” and “externalIPs” services. Both of these options have significant downsides for production use, which makes bare-metal clusters second-class citizens in the Kubernetes ecosystem.

MetalLB aims to redress this imbalance by offering a network load balancer implementation that integrates with standard network equipment, so that external services on bare-metal clusters also “just work” as much as possible.

## Treafik

Traefik is a leading modern reverse proxy and load balancer that makes deploying microservices easy. Traefik integrates with your existing infrastructure components and configures itself automatically and dynamically.

Traefik is designed to be as simple as possible to operate, but capable of handling large, highly-complex deployments across a wide range of environments and protocols in public, private, and hybrid clouds. It also comes with a powerful set of middlewares that enhance its capabilities to include load balancing, API gateway, orchestrator ingress, as well as east-west service communication and more.

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

## Emissary-ingress

Emissary-Ingress is an open-source Kubernetes-native API Gateway + Layer 7 load balancer + Kubernetes Ingress built on Envoy Proxy. Emissary-ingress is a CNCF incubation project (and was formerly known as Ambassador API Gateway.)

Emissary-ingress enables its users to:

Manage ingress traffic with load balancing, support for multiple protocols (gRPC and HTTP/2, TCP, and web sockets), and Kubernetes integration
Manage changes to routing with an easy to use declarative policy engine and self-service configuration, via Kubernetes CRDs or annotations
Secure microservices with authentication, rate limiting, and TLS
Ensure high availability with sticky sessions, rate limiting, and circuit breaking
Leverage observability with integrations with Grafana, Prometheus, and Datadog, and comprehensive metrics support
Enable progressive delivery with canary releases
Connect service meshes including Consul, Linkerd, and Istio
Knative serverless integration

## Sentinel 

As distributed systems become increasingly popular, the reliability between services is becoming more important than ever before. Sentinel takes "flow" as breakthrough point, and works on multiple fields including flow control, traffic shaping, circuit breaking and system adaptive protection, to guarantee reliability and resilience for microservices##

Sentinel has the following features:

Rich applicable scenarios: Sentinel has been wildly used in Alibaba, and has covered almost all the core-scenarios in Double-11 (11.11) Shopping Festivals in the past 10 years, such as “Second Kill” which needs to limit burst flow traffic to meet the system capacity, message peak clipping and valley fills, circuit breaking for unreliable downstream services, cluster flow control, etc.
Real-time monitoring: Sentinel also provides real-time monitoring ability. You can see the runtime information of a single machine in real-time, and the aggregated runtime info of a cluster with less than 500 nodes.
Widespread open-source ecosystem: Sentinel provides out-of-box integrations with commonly-used frameworks and libraries such as Spring Cloud, Dubbo and gRPC. You can easily use Sentinel by simply add the adapter dependency to your services.
Polyglot support: Sentinel has provided native support for Java, Go and C++.
Various SPI extensions: Sentinel provides easy-to-use SPI extension interfaces that allow you to quickly customize your logic, for example, custom rule management, adapting data sources, and so on.

## Kong

Distributed architectures and microservices can accelerate development cycles and reduce costs. But cloud native apps bring new challenges in providing reliable connectivity.

## Service Mesh

Service meshes manage traffic (i.e. communication) between services. They enable platform teams to add reliability, observability, and security features uniformly across all services running within a cluster without requiring any code changes.

Along with Kubernetes, service meshes have become some of the most critical infrastructure components of the cloud native stack.

* Linkerd
* Istio
* Consul
* Meshery
* Open Service Mesh

## Linkerd

Linkerd is an open-source network proxy developed by Buoyant to be installed as a service mesh. Linkerd is one of the first products to be associated with the term service mesh and supports platforms such as Docker and Kubernetes.

## Istio

Istio extends Kubernetes to establish a programmable, application-aware network using the powerful Envoy service proxy. Working with both Kubernetes and traditional workloads, Istio brings standard, universal traffic management, telemetry, and security to complex deployments.

## Consul

Consul is a service mesh solution providing a full featured control plane with service discovery, configuration, and segmentation functionality. Each of these features can be used individually as needed, or they can be used together to build a full service mesh. Consul requires a data plane and supports both a proxy and native integration model. Consul ships with a simple built-in proxy so that everything works out of the box, but also supports 3rd party proxy integrations such as Envoy.





As we've seen, tools in this layer deal with how all these independent containerized services are managed as a group. Orchestration and scheduling tools can be thought of as a cluster OS managing containerized applications across your cluster. Coordination and service discovery, service proxies, and service meshes ensure services can find each other and communicate effectively in order to collaborate as one cohesive app. API gateways are an additional layer providing even more control over service communication, in particular between external applications. Next, we'll discuss the application definition and development layer — the last layer of the CNCF landscape. It covers databases, streaming and messaging, application definition, and image build, as well as continuous integration and deliver.
