# Kubernetes Basics learning day 1

## 1. What is Kubernetes?

Kubernetes (often abbreviated as K8s) is an open-source container orchestration platform. It automates the deployment, scaling, management, and operation of applications in containers. It simplifies the process of managing applications made up of multiple containers, which can be spread across different environments.

## 2. The Kubernetes Trilogy

The Kubernetes Trilogy consists of three key components that help in managing applications:

- **Containers:** These are lightweight, executable units that combine application code with all the necessary dependencies (libraries, frameworks, etc.), allowing software to run reliably from one computing environment to another.

- **Orchestration:** This refers to the automated management of containerized applications. Kubernetes serves as the orchestrator that helps manage container lifecycles, ensuring they run as intended.

- **Microservices:** This is an architectural style where applications are developed as a collection of loosely coupled services. Kubernetes is particularly well-suited for microservices architecture, allowing developers to manage and scale individual services independently.

## 3. Containers Overview

Containers are a form of virtualization that allows you to package an application and its dependencies in a single unit. Here are a few key points:

- Containers run in their isolated environments, ensuring that they do not interfere with each other.
  
- Since containers encapsulate everything needed to run an application, they can easily be moved across different environments (development, testing, production).
  
- Containers share the host system's kernel, making them lightweight compared to traditional virtual machines, which require a full operating system for each instance.

## 4. Container Orchestration

Container orchestration refers to the automated arrangement, coordination, and management of containerized application components. Key benefits include:

- **Scaling:** Automatically adjust the number of active containers in response to load (up or down).
  
- **Load Balancing:** Distribute traffic evenly across containers to ensure reliability and performance.
  
- **Fault Tolerance:** Automatically restart failed containers and redistribute workloads to maintain application availability.
  
- **Deployment Automation:** Simplify the process of deploying updates and rollbacks.

## 5. Kubernetes Architecture

Kubernetes has a master-slave architecture, where multiple components interact to manage the containerized applications effectively. Here are the main components:

### Control Plane (Master Node)

- **API Server:** The front-end for the Kubernetes control plane that exposes the Kubernetes API.
  
- **Scheduler:** Assigns work to the nodes based on resource availability and other constraints.
  
- **Controller Manager:** Responsible for regulating the state of the cluster (like replication and scaling).
  
- **etcd:** A distributed key-value store used for storing all the cluster data and state information.

### Worker Nodes (Minions)

- **Kubelet:** An agent running on each worker node that manages containerized applications.
  
- **Kube-proxy:** Handles network routing for services in the cluster, enabling communication between components.
  
- **Containers:** The applications running inside isolated environments on these nodes, typically managed through tools like Docker.

# Kubernetes Node Architecture

In a Kubernetes cluster, the architecture is divided into two main types of nodes: **master nodes** and **worker nodes**. Each type serves a distinct role in managing containerized applications. Here’s a breakdown of the differences between the two:

| Aspect                       | Master Node                                            | Worker Node                                            |
|------------------------------|-------------------------------------------------------|-------------------------------------------------------|
| **Role**                     | Responsible for overall management and orchestration of the Kubernetes cluster. | Hosts applications and services deployed in the cluster. |
| **Control Plane**            | Acts as the control plane, making decisions about the cluster (e.g., scheduling, scaling). | Executes workloads and runs the actual applications.   |
| **Key Components**           |  - **API Server:** Front-end for the control plane, processing all RESTful requests.  <br> - **Scheduler:** Assigns workloads based on resource availability. <br> - **Controller Manager:** Regulates the state of the cluster. <br> - **etcd:** Distributed key-value store for all cluster data and state information. |  - **Kubelet:** Ensures that containers are running in a Pod as per specifications. <br> - **Kube-proxy:** Manages network routing and load balancing. <br> - **Container Runtime:** Software to run containers (e.g., Docker, containerd). |
| **Management**               | Single point of management for the cluster, often configured for high availability. | Multiple worker nodes can be scaled up or down based on demand. |
| **User Applications**        | Does not run user applications or workloads; primarily management functions. | Runs user applications, essential for application performance and availability. |

# Virtualization Vs Containerization
| Feature             | Virtualization                                           | Containerization                                    |
|---------------------|---------------------------------------------------------|----------------------------------------------------|
| **Architecture**    | Each VM runs a full OS on top of a hypervisor.         | Containers share the host OS kernel and run isolated processes. |
|                     | VMs include the application, its dependencies, and a complete OS, leading to resource overhead. | Containers include the application and its dependencies, relying on the host OS kernel. |
| **Resource Efficiency** | VMs are resource-intensive and can lead to inefficient usage. | Containers are lightweight, consuming fewer resources, and can start almost instantly. |
| **Isolation**       | Strong isolation; each VM runs its own OS instance, enhancing security. | Less isolation; containers share the same kernel, leading to potential security concerns. |
| **Portability**     | VMs can be moved between hypervisors but may require significant setup. | Highly portable; run anywhere with a container runtime, making movement across environments seamless. |
| **Management**      | More complex management due to multiple full systems.   | Simplified management and orchestration via tools like Kubernetes, suitable for microservices. |

**Quick Note**: Containers provide a lightweight, efficient, and portable method for running applications by sharing the host OS kernel, whereas virtualization offers strong isolation but tends to be heavier due to separate OS instances. Organizations often choose based on use cases, performance requirements, and deployment strategies.