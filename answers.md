# CCS3308 – Virtualization and Containers
# Lab 06 – Kubernetes Fundamentals with Minikube
# Checkpoint Answers

---

## Q1. Explain the difference between the control plane and a worker node.

The control plane manages the Kubernetes cluster and makes decisions about the cluster state. It contains components such as the API Server, Scheduler, Controller Manager, and etcd.

A worker node runs application workloads. It contains components such as kubelet, kube-proxy, and the container runtime. Worker nodes execute Pods assigned by the control plane.

---

## Q2. What happens when you manually delete a Pod managed by a Deployment?

When a Pod managed by a Deployment is deleted, Kubernetes detects that the actual number of Pods is lower than the desired replica count.

The Deployment controller automatically creates a replacement Pod to maintain the required number of replicas. This feature is called Kubernetes self-healing.

---

## Q3. How does scaling a Deployment affect the number of Pods?

Scaling a Deployment changes the desired number of replicas.

When scaling up, Kubernetes creates additional Pods until the required number is reached.

When scaling down, Kubernetes removes extra Pods while maintaining the new desired replica count.

---

## Q4. What is the purpose of a Kubernetes Service?

A Kubernetes Service provides stable network access to a group of Pods.

Since Pods are temporary and their IP addresses can change, a Service provides a fixed endpoint and forwards traffic to available Pods using label selectors.

---

## Q5. Difference between ClusterIP and NodePort.

### ClusterIP

ClusterIP exposes a Service only inside the Kubernetes cluster. It is mainly used for internal communication between applications.

### NodePort

NodePort exposes a Service outside the cluster by opening a port on each Kubernetes node. Users can access the application using the node IP and port number.

---

## Q6. Explain how Kubernetes performs rolling updates.

Kubernetes performs rolling updates by gradually replacing old Pods with new Pods.

The Deployment creates new Pods with the updated image while keeping old Pods running until the new Pods are ready. This allows applications to be updated with minimal downtime.

---

## Q7. How can you rollback a Deployment?

A Deployment can be rolled back using:

