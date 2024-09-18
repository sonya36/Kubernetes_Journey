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