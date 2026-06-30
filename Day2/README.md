# Day 2

## Info - Container Orchestration Platform
<pre>
- in order to deploy your application into Container Orchestration Platform, we must first containerize them
- In real world applications, no one manages containerized application workloads manually
- In real world, Container Orchestration Platforms manage our containerized application workloads
- They provide
  - in-built monitoring, health-check, readiness check, liveliness check for your application
  - self-healing to your applications
  - a way to scale up/down your application instances based on user traffic
  - rolling update
    - upgrading your application from one version to other without any downtime
    - rolling back to earlier stable versions are also possible
  - ways to collect performance metrics
- any container orchestration platform works as a cluster of many nodes
- nodes are nothing but Physical Servers or Virtual Machines in private/public cloud
- examples
  - Docker SWARM
  - Kubernetes
  - Rancher
  - Red Hat Openshift
  - AWS eks
  - AWS ROSA
  - Azure aks
  - Azure ARO
</pre>

## Info - Docker SWARM
<pre>
- is developed by Docker Inc as an open-source project
- it supported only Docker Containerized applications
- it is a very light-weight setup that works in laptop/dekstop with normal configurations
- it is ideal setup for learning purpose
- it is ideal for Dev/QA environment
</pre>

## Info - Kubernetes
<pre>
- is a Container Orchestration platform developed in Golang by Google
- intially it was called borg, Google has been using this container orchestration platforms internally within google
  for several years
- it is production-grade because google used it on complex projects many years
- it supports many different container runtimes/engines
- Kubernetes supports something called CRI(Container Runtime Interface)
- any container runtime/engine that must be supported by Kubernetes they have to implement the CRI
- Kubernetes can/will interact with any type of Container Runtime/Engine via CRI
- Kubernetes supports 2 types of nodes
  - Master Node
    - this is where Control Plane components will be running
    - Control Plane Components
      1. API Server
      2. etcd key/value database
      3. scheduler
      4. Controller Managers( collection of many controllers )
  - Worker Node
    - this is where user applications will be running
- Kubernetes is primarily a CLI application
- Kubernetes doesn't support 
  - a production-grade webconsole
  - User Management
  - Internal Container Registry ( out of box )
  - Prometheus/Grafana performance metrics collection ( out of box )
- Kubernetes supports basic building blocks to extend the Kubernetes features by adding
  - your own custom resources
  - your own custom controllers
- Kubernetes allows one to deploy their application only from a Container Image
- In Kubernetes Master/Worker nodes, we can choose to install any Linux OS distribution (ubuntu, rocky, fedora, RHEL, etc., )
</pre>


## Info - Red Hat Openshift
<pre>
- is a Red Hat's distribution of Kubernetes
- Openshift is developed on top of opensource Kubernetes
- Hence, Openshift is a superset of Kubernetes
- Openshift is Kubernetes with batteries included
- Openshift comes with these additional features on top of what is already supported by Kubernetes
  1. User Management
  2. Production Web-console (GUI)
  3. Many additional features
     - Route
     - S2I ( Source to Image )
       - one can deploy their application from plain source code coming from GitHub or any other version control
       - supports many different strategies
         - docker
         - source
         - pipeline
  4. Internal Container Registry
- Red Hat acqurired a company named CoreOS
  - CoreOS organization had several interesting products
    - rkt(pronounced as Rocket) - container runtime
    - CoreOS - Linux based minimal & secure operating system good enough for Container Orchestration Platform
    - Network addons - Flannel
- Red Hat Openshift starting from v4.x,
  - supports only Red Hat Enterprise CoreOS operating (RHCOS) in Master Nodes
  - supports either Red Hat Enterprise Linux(RHEL) or RHCOS in Worker Node
  - Red Hat Openshift generally recommends to install RHCOS in all nodes
  - supports only CRI-O Container Runtime
  - RHCOS Operating System
    - is an Container Orchestration Platform optimized minimal and secured Operating System
      based on RHEL
    - this OS comes with CRI-O & Podman pre-installed
    - it is an immutable OS many restrictions
    - some of the folders like /var, /bin, /usr/bin are all treated as read-only folder
    - only through Machine Config Operators we can update certain reserved folders, meaning
      application won't be able to modify those restricted folders
    - Ports 0-1024 are reserved for Openshift's internal use
</pre>
