# Provisioning

Provisioning is the first layer in the cloud native landscape. It encompasses tools that are used to create and harden the foundation on which cloud native apps are built. You'll find tools to automatically configure, create, and manage the infrastructure, as well as for scanning, signing, and storing container images. The layer also extends to security with tools that enable policy setting and enforcement, embedded authentication and authorization, and the handling of secrets distribution. 

##  Automation & Configuration

Automation and configuration tools speed up the creation and configuration of compute resources (virtual machines, networks, firewall rules, load balancers, etc.).

Tools of this category allow engineers to build computing environments without human intervention.

* Ansible
* Chef
* Puppet
* Terraform
* KubeEdge
* Openstack
* SaltStack

## Container Registry

Container registries are specialized web applications that categorize and store repositories.

Cloud native applications are packaged and run as containers. Container registries store and provide the container images needed to run these apps.

By centrally storing all container images in one place, they are easily accessible for any developer working on that app.

* Dragonfly
* Harbor
* Quay
* Kraken

##  Security & Compliance

Tools and projects in this section provide some of the abilities needed to build and run modern applications securely.

Security and compliance tools help harden, monitor, and enforce platform and application security. From containers to Kubernetes environments, these tools allow you to set policy (for compliance), get insights into existing vulnerabilities, catch misconfigurations, and harden the containers and clusters.

* Falco
* In-toto
* Notary
* Open Policy Agency
* TUF
* cert-manager
* Keylime
* Sonobuoy
* Trivy

## Key Management

A key is a string of characters used to encrypt or sign data. Like a physical key, it locks (encrypts) data so that only someone with the right key can unlock (decrypt) it.

The tools and projects in this category cover everything from how to securely store passwords and other secrets (sensitive data such as API keys, encryption keys, etc.) to how to safely eliminate passwords and secrets from your microservices environment.

Tools in this category can be grouped into two sets: 

1) key generation, storage, management, and rotation
2) single sign-on and identity management.

* SPIFFE
* SPIRE
* KeyCloak
* Hashicorp Vault
* Teleport
* ORY Hydra