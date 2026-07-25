# 1. Kafka Fundamentals

* Event Streaming
* Distributed Log
* Pub/Sub
* Message Queue vs Event Streaming
* Kafka Ecosystem
* Kafka Use Cases
* Kafka Architecture

---

# 2. Core Components

* Broker
* Cluster
* Topic
* Partition
* Offset
* Producer
* Consumer
* Consumer Group
* Controller
* Metadata
* KRaft Architecture (ZooKeeper Removal)

---

# 3. Record Structure

* Key
* Value
* Headers
* Timestamp
* Offset
* Partition
* Serialization
* Compression

---

# 4. Topics & Partitions

* Topic Creation
* Partitioning
* Partition Assignment
* Partition Expansion
* Partition Ordering
* Log Segments
* Retention
* Compaction

---

# 5. Producers

* Producer API
* Partitioner
* Acknowledgements (acks)
* Retries
* Idempotent Producer
* Transactions
* Compression
* Batching
* Buffer Management
* Delivery Timeout
* Producer Interceptors

---

# 6. Consumers

* Consumer API
* Poll Loop
* Offset Management
* Auto Commit
* Manual Commit
* Consumer Groups
* Rebalancing
* Cooperative Rebalancing
* Static Membership
* Pause & Resume

---

# 7. Delivery Semantics

* At Most Once
* At Least Once
* Exactly Once
* Idempotent Writes
* Transactional Messaging
* End-to-End Exactly Once

---

# 8. Replication

* Leader Replica
* Follower Replica
* ISR (In-Sync Replicas)
* Leader Election
* Replica Lag
* High Watermark
* Replica Fetching

---

# 9. Fault Tolerance

* Broker Failure
* Controller Failure
* Leader Failure
* Partition Recovery
* Replica Recovery
* Network Partition
* Rack Awareness

---

# 10. Storage Internals

* Commit Log
* Log Segments
* Index Files
* Offset Index
* Time Index
* Log Compaction
* Log Cleanup
* Retention Policies

---

# 11. Offset Management

* Consumer Offsets
* Offset Storage
* Offset Reset
* Commit Strategies
* Replay
* Seeking
* Lag Measurement

---

# 12. Ordering & Partitioning

* Ordering Guarantees
* Key-Based Partitioning
* Custom Partitioners
* Global Ordering Limitations
* Partition Affinity

---

# 13. Transactions

* Transaction Coordinator
* Transaction IDs
* Commit
* Abort
* Producer Transactions
* Consumer Transactions
* Read Committed Isolation

---

# 14. Serialization

* String
* JSON
* Avro
* Protobuf
* Custom Serialization
* Schema Evolution
* Schema Compatibility

---

# 15. Schema Registry

* Schema Registry
* Subject Naming
* Compatibility Modes
* Versioning
* Schema Evolution
* Producer Validation
* Consumer Validation

---

# 16. Performance

* Batch Size
* Linger.ms
* Compression
* Fetch Size
* Max Poll Records
* Parallel Consumers
* Throughput Optimization
* Latency Optimization

---

# 17. Kafka Streams

* Streams API
* Topology
* Stateless Processing
* Stateful Processing
* KStream
* KTable
* GlobalKTable
* Windowing
* Joins
* Interactive Queries

---

# 18. Connect

* Kafka Connect
* Source Connectors
* Sink Connectors
* SMT (Single Message Transform)
* Connector Scaling
* Error Handling

---

# 19. Event-Driven Architecture

* Event Sourcing
* CQRS
* Choreography
* Orchestration
* Saga Pattern
* Outbox Pattern
* CDC Integration

---

# 20. Security

* SSL/TLS
* SASL
* SCRAM
* OAuth
* ACLs
* RBAC
* Encryption
* Authentication
* Authorization

---

# 21. Monitoring

* Consumer Lag
* Broker Metrics
* Topic Metrics
* Partition Metrics
* JMX
* Prometheus
* Grafana
* Cruise Control
* Health Monitoring

---

# 22. High Availability

* Multi Broker Cluster
* Rack Awareness
* Cross AZ Deployment
* Disaster Recovery
* MirrorMaker 2
* Cluster Linking
* Multi Region Replication

---

# 23. Scaling

* Horizontal Scaling
* Broker Scaling
* Partition Scaling
* Consumer Scaling
* Producer Scaling
* Capacity Planning
* Rebalancing Strategy

---

# 24. Spring Integration

* Spring for Apache Kafka
* KafkaTemplate
* @KafkaListener
* Listener Containers
* Error Handlers
* Retry Topics
* Dead Letter Topics
* Transactions
* Batch Consumers
* Reactive Integration

---

# 25. Cloud Kafka

* Confluent Cloud
* Amazon MSK
* Azure Event Hubs (Kafka API)
* Managed Kafka
* Kubernetes Deployments
* Strimzi

---

# 26. Kafka Internals

* Network Layer
* Request Handling
* Fetch Requests
* Produce Requests
* Controller Internals
* Metadata Propagation
* Partition Assignment
* Group Coordinator
* Consumer Coordinator
* KRaft Consensus

---

# 27. Data Lifecycle

* Retention Policies
* Log Compaction
* Tombstone Records
* Data Cleanup
* Archive Strategy
* Replay Strategy

---

# 28. Best Practices

* Topic Naming
* Partition Count Planning
* Key Selection
* Idempotent Producers
* Dead Letter Topics
* Retry Strategy
* Backpressure Handling
* Schema Evolution
* Observability
* Capacity Planning

---

# 29. Common Production Problems

* Consumer Lag
* Hot Partitions
* Partition Skew
* Rebalance Storms
* Duplicate Messages
* Message Loss
* ISR Shrinkage
* Leader Election Delays
* Disk Saturation
* Large Messages
* Serialization Errors
* Schema Compatibility Issues
* Broker Memory Pressure
* Network Bottlenecks
* Slow Consumers

---

# 30. Interview Focus Areas (Staff/Principal)

* Kafka Internal Architecture
* KRaft vs ZooKeeper
* Producer Internals
* Consumer Internals
* Offset Management Strategy
* Partitioning Strategy
* Ordering Guarantees
* Exactly Once Processing
* Transaction Internals
* Replication Internals
* Leader Election
* Log Compaction vs Retention
* Consumer Rebalancing
* Performance Tuning
* Capacity Planning
* Multi-region Architecture
* Event-Driven Design
* Outbox vs CDC
* Failure Recovery
* Production Troubleshooting

---
