# 🚀 30 Kubernetes Interview Questions Every DevOps Engineer Should Know

## Beginner Level

### 1. What is Kubernetes?
**Answer:** Kubernetes (K8s) is an open-source container orchestration platform used to deploy, scale, and manage containerized applications.

**Example:** Automatically scaling an ECS-like microservices platform from 3 to 10 pods during traffic spikes.

### 2. What is a Pod?
**Answer:** The smallest deployable unit in Kubernetes. A pod can contain one or more tightly coupled containers.

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx
spec:
  containers:
  - name: nginx
    image: nginx
```

### 3. What is a Node?
**Answer:** A worker machine (VM or physical server) where pods run.

### 4. What is a Cluster?
**Answer:** A collection of control plane and worker nodes.

### 5. What is a Deployment?
**Answer:** Manages stateless applications, rolling updates, and replica management.

```bash
kubectl rollout restart deployment app
```

### 6. What is a Service?
**Answer:** Provides stable networking access to pods.

**Types:** ClusterIP, NodePort, LoadBalancer, ExternalName.

### 7. What is a Namespace?
**Answer:** Logical isolation of Kubernetes resources.

```bash
kubectl get pods -n dev
```

### 8. What is a ConfigMap?
**Answer:** Stores non-sensitive configuration.

### 9. What is a Secret?
**Answer:** Stores sensitive information like passwords and API keys.

### 10. What is a ReplicaSet?
**Answer:** Ensures desired number of pod replicas are running.

---

## Intermediate Level

### 11. What is a StatefulSet?
**Answer:** Used for stateful applications like MySQL, Kafka, Redis.

**Features:** Stable hostname, persistent storage.

### 12. What is a DaemonSet?
**Answer:** Ensures one pod runs on every node.

**Examples:** FluentBit, Datadog Agent, Node Exporter.

### 13. What is Ingress?
**Answer:** Layer-7 HTTP/HTTPS routing to services.

### 14. What is an Ingress Controller?
**Answer:** Component that implements ingress rules.

**Examples:** NGINX, AWS Load Balancer Controller, Traefik.

### 15. What is a Persistent Volume (PV)?
**Answer:** Cluster storage resource.

### 16. What is PVC?
**Answer:** Persistent Volume Claim requesting storage.

### 17. What is HPA?
**Answer:** Horizontal Pod Autoscaler automatically scales pods.

```bash
kubectl autoscale deployment app --cpu-percent=70 --min=2 --max=10
```

### 18. What is a Readiness Probe?
**Answer:** Determines whether a pod can receive traffic.

### 19. What is a Liveness Probe?
**Answer:** Determines whether a container should be restarted.

### 20. What is RBAC?
**Answer:** Role-Based Access Control used for authorization.

---

## Advanced Level

### 21. What is etcd?
**Answer:** Distributed key-value database storing cluster state.

### 22. What is kubelet?
**Answer:** Node agent that ensures containers are running.

### 23. What is kube-proxy?
**Answer:** Handles service networking and iptables/IPVS rules.

### 24. What are Taints & Tolerations?
**Answer:** Restrict pod scheduling onto specific nodes.

```bash
kubectl taint nodes node1 dedicated=gpu:NoSchedule
```

### 25. What is Node Affinity?
**Answer:** Schedule pods based on node labels.

### 26. What is a Network Policy?
**Answer:** Controls ingress and egress pod traffic.

### 27. What is a PDB?
**Answer:** Pod Disruption Budget ensuring minimum application availability during maintenance.

### 28. What is Helm?
**Answer:** Kubernetes package manager.

```bash
helm install nginx bitnami/nginx
```

### 29. How do you troubleshoot Pending Pods?

1. `kubectl describe pod`
2. Check CPU/Memory requests
3. Verify node selectors, taints, affinity
4. Verify PVC binding

### 30. How do you troubleshoot CrashLoopBackOff?

1. `kubectl logs <pod>`
2. `kubectl describe pod`
3. Verify probes
4. Verify environment variables and secrets
5. Check OOMKilled events

---

# Common Real-Time Interview Scenarios

- Upgrade EKS cluster with zero downtime.
- Restrict namespaces using RBAC.
- Troubleshoot CoreDNS failures.
- Configure HPA and Cluster Autoscaler.
- Implement Network Policies for microservices isolation.

