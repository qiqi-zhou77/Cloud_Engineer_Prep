# Intro to Kubernetes Engine
***Container Orchestrator***
K8s runs containers on a cluster of VMs.It determines where to run containers, monitor the health of containers and manages the full life cycle of VM instances. 

## Kubernetes Cluster Architecture
- Consist of control plane and one or more worker machines, nodes
- Control plane manages services provided by K8s,such as K8s API, controllers, and schedulers.
- All interactions with the cluster are done throu the control plane using the K8s API or kubectl commands
- Scheduler: assign pods to nodes
- etcf, key calue store
- Kubelet, an agent that runs on each node in a cluster, service that commuinicates with the control pane
- Container runtime, the software responsible for running containers
- Kube proxy, a network proxy that runs on each node in the cluster

Nodes execute the workloads run on the cluster. Nodes are VMs that run containers configured to run an application

Nodes are the individual machines (physical or virtual) that form the underlying infrastructure of a Kubernetes cluster. These nodes are responsible for running pods and handling containerized workloads.

## Kubernetes Objects

**Pods**:
 - Single instance of a running process in a cluster. Pods contain at least one container
 - Pods use shared networking and storage across containers.
 - Each pod has a unique IP address and a set of ports
 - Multiple containers in a pod connect to diff ports and can talk to each other on localhost
 - Supports autoscalling and ephemeral

***the mechanism that manages scaling and health monitroing is known as controller***

**Services**
 - Pods are ephemeral and can be termincated by a controller, other services that depends on pods should not be tightly coupled to particular pods
 - Service is a level of indirection between applications running in pods and other applications that call them
 - It provides API end points with a stable IP address that allow application to discover pods runnint a particular application. It maintains an up to date list of pods running an application

**Deployments**
 - sets of identical pods running the same application
 - Pod template is a definition of how to run a pod. Pod specification is how to define the pod

**ReplicaSets**
 - controller used by deployment that ensure the conrrect number of identical pods are running
 - also used to updateand delete pods

**StatefulSets**
 - there are times, when it is advantageous to have a single pod respond to all calls for a client during a single session
 - used when an application needs a unique network identifier or stable persistent storage

**Jobs**
 - An abstraction about a workload
 - Jobs create pods and run them until the application complets a workload

**Volumes**
 - Storage mechamism independent of life of a pod

**Namespaces**
 - Logical abstraction for separating groups of resources in a cluster
 - Kubernetes resources such as pods, services, deployments, and replication controllers can be scoped to a specific namespace.

**Node Pools**
 - A set of nodes in a cluster that have the same config


Namespaces are used to organize and isolate Kubernetes resources within a cluster, providing logical separation and resource management at the application level.

Node pools, on the other hand, are used to manage the underlying compute resources (nodes) within a cluster, allowing administrators to scale, customize, and manage nodes collectively.

Namespaces provide logical isolation and organization of Kubernetes resources, while node pools manage the underlying compute resources within a cluster. Both concepts are essential for efficient resource management and workload isolation in Kubernetes environments.



# Deploying Kubernetes Cluster
## Deployment using cloud console
- need to enable k8s api
## Deployment using cloud shell and sdk
- Lue
# Deploying Application Pods


# Monitoring Kubernetes
- CLoud Operting Suite --> Cloud monitoring and Cloud logging services
 - System metrics
 - Prometheus
 - Workload Metrics

***Connection and Comparison Of VMs and Containers***

- Virtual Machine (VM):

    * A virtual machine is an emulation of a physical computer system.
    * VMs allow you to run multiple operating systems and applications on a single physical machine, known as the host.
    * Each VM includes its own virtualized hardware, such as CPU, memory, storage, and network interfaces.
    * VMs are typically run using a hypervisor, which manages and allocates physical resources to the VMs.
    * VMs provide isolation at the hardware level, allowing each VM to run its own complete operating system with its own kernel.

- Container:

    * A container is a lightweight, portable, and self-sufficient unit that packages an application and its dependencies.
    * Containers share the host system's operating system kernel but are isolated from each other at the user-space level.
    * Containers leverage features of the host operating system's kernel, such as namespaces and control groups (cgroups), to provide resource isolation and control.
    * Containers are typically managed by container runtimes like Docker or container orchestration platforms like Kubernetes.
    * Containers are often used to build, deploy, and run applications consistently across different environments, from development to production.


- Differences:

    * VMs emulate full-fledged hardware, including a virtual CPU, memory, storage, and network interfaces, while containers share the host system's kernel and only package the application and its dependencies.
    * VMs tend to be heavier in terms of resource consumption because they require a separate guest operating system for each VM. Containers, on the other hand, are lightweight and consume fewer resources because they share the host's kernel and libraries.
    * VMs provide stronger isolation between applications since each VM has its own kernel and operates like an independent physical machine. Containers offer less isolation because they share the host's kernel but provide sufficient isolation for many use cases.


- Connection:

    * Both containers and VMs are used for virtualization, enabling the efficient use of hardware resources by running multiple applications or workloads on a single physical machine.
    * Containers and VMs can be used together in hybrid environments. For example, you can run containerized applications within VMs for additional isolation or security, or you can run VMs within containers for specialized use cases.
    * Container orchestration platforms like Kubernetes can manage both containers and VMs, allowing organizations to deploy and manage applications across mixed infrastructure environments seamlessly.
