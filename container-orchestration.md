# 1. Container Fundamentals

* Virtual Machines vs Containers
* OCI Standards
* Container Architecture
* Container Runtime
* Namespaces
* cgroups
* Union Filesystems
* Process Isolation
* Resource Isolation

---

# 2. Docker Fundamentals

* Docker Architecture
* Docker Engine
* Docker CLI
* Docker Desktop
* Docker Daemon
* Docker API
* Images
* Containers
* Registries

---

# 3. Docker Images

* Image Layers
* Layer Caching
* Base Images
* Minimal Images
* Distroless Images
* Multi-stage Builds
* Image Tagging
* Image Digest
* Image Signing

---

# 4. Dockerfile

* Instructions
* Build Context
* COPY vs ADD
* ENTRYPOINT
* CMD
* ENV
* ARG
* WORKDIR
* USER
* HEALTHCHECK
* Best Practices

---

# 5. Container Lifecycle

* Create
* Start
* Pause
* Restart
* Stop
* Remove
* Health Checks
* Restart Policies
* Graceful Shutdown

---

# 6. Storage

* Volumes
* Bind Mounts
* tmpfs
* Persistent Storage
* Volume Drivers
* Storage Classes (Kubernetes)

---

# 7. Container Networking

* Bridge Network
* Host Network
* Overlay Network
* Macvlan
* DNS
* Service Discovery
* Port Mapping

---

# 8. Container Runtime

* containerd
* CRI-O
* runc
* OCI Runtime
* Runtime Interface
* Image Pulling
* Runtime Security

---

# 9. Kubernetes Fundamentals

* Cluster
* Control Plane
* Worker Node
* API Server
* etcd
* Scheduler
* Controller Manager
* Kubelet
* Kube Proxy

---

# 10. Kubernetes Objects

* Pod
* ReplicaSet
* Deployment
* StatefulSet
* DaemonSet
* Job
* CronJob
* Namespace

---

# 11. Services & Networking

* ClusterIP
* NodePort
* LoadBalancer
* ExternalName
* Headless Service
* Ingress
* Gateway API
* Service Discovery
* DNS

---

# 12. Scheduling

* Scheduler
* Node Selector
* Node Affinity
* Pod Affinity
* Anti-Affinity
* Taints
* Tolerations
* Topology Spread Constraints
* Priority Classes

---

# 13. Scaling

* Horizontal Pod Autoscaler (HPA)
* Vertical Pod Autoscaler (VPA)
* Cluster Autoscaler
* Manual Scaling
* Resource Requests
* Resource Limits

---

# 14. Configuration Management

* ConfigMaps
* Secrets
* Environment Variables
* Projected Volumes
* Secret Rotation
* Dynamic Configuration

---

# 15. Storage in Kubernetes

* Persistent Volumes
* Persistent Volume Claims
* Storage Classes
* CSI
* Dynamic Provisioning
* Stateful Applications

---

# 16. Kubernetes Networking

* CNI
* Pod Network
* Network Policies
* DNS
* Service Mesh Integration
* Ingress Controllers
* Egress Control

---

# 17. Security

* RBAC
* Service Accounts
* Pod Security Standards
* Admission Controllers
* Security Context
* Image Security
* Secret Management
* Network Policies
* mTLS

---

# 18. OpenShift

* OpenShift Architecture
* Routes
* Projects
* SCC (Security Context Constraints)
* Operators
* Image Streams
* BuildConfig
* DeploymentConfig (legacy awareness)

---

# 19. Service Mesh

* Istio
* Linkerd
* Sidecars
* Traffic Management
* mTLS
* Retry
* Circuit Breaker
* Canary Routing
* Observability

---

# 20. Operators

* Operator Pattern
* Operator Lifecycle Manager (OLM)
* Custom Resources (CRDs)
* Controllers
* Reconciliation Loop

---

# 21. Observability

* Logs
* Metrics
* Traces
* Events
* OpenTelemetry
* Prometheus
* Grafana
* Loki
* Jaeger

---

# 22. Deployment Strategies

* Rolling Update
* Blue-Green
* Canary
* A/B Deployment
* Shadow Deployment
* Progressive Delivery
* Rollback

---

# 23. CI/CD Integration

* GitOps
* Argo CD
* Flux
* GitHub Actions
* Jenkins
* Harness
* Image Promotion
* Deployment Pipelines

---

# 24. Performance

* Resource Optimization
* CPU Limits
* Memory Limits
* JVM Tuning in Containers
* Startup Optimization
* Image Optimization
* Scheduling Optimization

---

# 25. High Availability

* Multi-Master Control Plane
* etcd HA
* Node Failure Recovery
* Pod Disruption Budgets
* Self-Healing
* Multi-AZ Clusters
* Disaster Recovery

---

# 26. Cloud Native Patterns

* Sidecar
* Ambassador
* Adapter
* Init Containers
* Ephemeral Containers
* Stateful Workloads
* Stateless Workloads

---

# 27. Kubernetes Internals

* API Server Internals
* Scheduler Algorithm
* etcd Architecture
* Kubelet Internals
* Reconciliation Loop
* Controller Pattern
* CRI
* CNI
* CSI

---

# 28. Best Practices

* Small Images
* Immutable Images
* Non-Root Containers
* Resource Requests/Limits
* Health Probes
* Graceful Shutdown
* Secrets Management
* GitOps
* Infrastructure as Code
* Observability by Default

---

# 29. Common Production Problems

* CrashLoopBackOff
* ImagePullBackOff
* OOMKilled
* Pending Pods
* Failed Scheduling
* DNS Resolution Failures
* Network Policy Misconfiguration
* PVC Binding Issues
* Node Not Ready
* etcd Performance Issues
* API Server Latency
* Resource Starvation
* Container Restart Loops
* Secret Rotation Failures
* Certificate Expiration
* Ingress Misconfiguration

---

# 30. Interview Focus Areas (Staff/Principal)

* Docker Internals
* OCI Runtime Architecture
* Container Isolation Mechanisms
* Kubernetes Control Plane Architecture
* Scheduler Internals
* Pod Lifecycle
* Networking Model
* Service Discovery
* CNI vs CSI vs CRI
* Deployment Strategies
* GitOps Architecture
* OpenShift vs Kubernetes
* Service Mesh Trade-offs
* Autoscaling Strategy
* High Availability Design
* Multi-Cluster Architecture
* Security Hardening
* Capacity Planning
* Production Troubleshooting
* Cost Optimization

---
