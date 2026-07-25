# 1. Redis Fundamentals

* In-Memory Database
* Cache vs Database
* Key-Value Store
* Redis Architecture
* Redis Use Cases
* Redis CLI
* Redis Stack Overview

---

# 2. Data Types

* String
* Hash
* List
* Set
* Sorted Set (ZSet)
* Bitmap
* Bitfield
* HyperLogLog
* Stream
* Geospatial
* Vector Sets (latest)

---

# 3. Key Management

* Key Naming
* Expiration (TTL)
* PTTL
* Persist
* Rename
* Delete
* Scan
* Keyspace Notifications
* Namespaces

---

# 4. CRUD Operations

* SET
* GET
* MSET
* MGET
* INCR / DECR
* APPEND
* Hash Operations
* List Operations
* Set Operations
* Sorted Set Operations
* Stream Operations

---

# 5. Caching Strategies

* Cache Aside (Lazy Loading)
* Read Through
* Write Through
* Write Behind (Write Back)
* Refresh Ahead
* Near Cache
* Read Around
* Negative Caching

---

# 6. Cache Consistency

* TTL-Based Consistency
* Explicit Invalidation
* Event-Driven Invalidation
* Version-Based Invalidation
* Double Delete Pattern
* Read-After-Write Consistency
* Eventual Consistency

---

# 7. Cache Problems

* Cache Miss
* Cache Hit Ratio
* Cache Stampede
* Cache Avalanche
* Cache Penetration
* Cache Breakdown (Hot Key Expiry)
* Hot Keys
* Cold Cache

---

# 8. Eviction Policies

* No Eviction
* LRU
* LFU
* Random
* TTL-Based Eviction
* Memory Limits
* Memory Fragmentation

---

# 9. Persistence

* RDB Snapshots
* AOF
* AOF Rewrite
* Hybrid Persistence
* fsync Policies
* Backup & Restore

---

# 10. Transactions

* MULTI
* EXEC
* WATCH
* DISCARD
* Optimistic Locking
* Lua Scripts
* Atomic Operations

---

# 11. Concurrency

* Single-Threaded Execution Model
* I/O Threads
* Atomicity
* Race Conditions
* Optimistic Concurrency
* Distributed Locks

---

# 12. Pub/Sub & Streams

* Pub/Sub
* Channels
* Pattern Subscriptions
* Redis Streams
* Consumer Groups
* Message Replay
* Dead Letter Handling (Application Level)

---

# 13. Distributed Redis

* Replication
* Primary-Replica
* Read Replicas
* Replication Lag
* Failover
* Redis Sentinel
* Redis Cluster

---

# 14. Partitioning & Scaling

* Hash Slots
* Sharding
* Client-side Sharding
* Cluster Sharding
* Resharding
* Slot Migration
* Cross-slot Operations

---

# 15. High Availability

* Sentinel
* Automatic Failover
* Cluster Failover
* Quorum
* Split Brain
* Multi-AZ Deployment
* Disaster Recovery

---

# 16. Performance

* Pipeline
* Batching
* Connection Pooling
* Command Complexity
* Memory Optimization
* Network Optimization
* Large Key Detection
* Hot Key Detection

---

# 17. Memory Management

* Memory Allocation
* Fragmentation
* Compression
* Object Encoding
* Lazy Free
* Active Defragmentation

---

# 18. Security

* Authentication
* ACLs
* Authorization
* TLS
* Encryption
* Protected Mode
* Network Isolation
* Secret Management

---

# 19. Monitoring

* INFO Command
* Slow Log
* Latency Monitor
* Memory Metrics
* Hit Ratio
* Replication Metrics
* Prometheus
* Grafana

---

# 20. Redis Modules

* RedisJSON
* RediSearch
* RedisBloom
* RedisTimeSeries
* RedisGears (where applicable)
* Vector Search

---

# 21. Spring Integration

* Spring Data Redis
* RedisTemplate
* StringRedisTemplate
* Reactive Redis
* CacheManager
* @Cacheable
* @CachePut
* @CacheEvict
* Serialization Strategies

---

# 22. Distributed Coordination

* Distributed Locking
* Redlock Algorithm
* Leader Election
* Rate Limiting
* Semaphore
* Token Bucket
* Sliding Window
* Unique ID Generation

---

# 23. Data Structures & Use Cases

* Session Store
* Shopping Cart
* Leaderboard
* Counters
* Rate Limiting
* Distributed Queue
* Job Queue
* Notification System
* Real-Time Analytics
* Presence Tracking

---

# 24. Redis Internals

* Event Loop
* Networking Model
* Command Execution
* Object Encoding
* Dictionary (Hash Table)
* Skip List
* SDS (Simple Dynamic String)
* Persistence Internals
* Replication Protocol

---

# 25. Cloud Redis

* Redis Cloud
* AWS ElastiCache
* Azure Cache for Redis
* Google Cloud Memorystore
* Managed Redis Best Practices

---

# 26. Best Practices

* Key Naming Strategy
* TTL Strategy
* Serialization Choice
* Avoid Large Keys
* Avoid Hot Keys
* Pipeline Usage
* Connection Pool Sizing
* Memory Sizing
* Cache Warm-up
* Observability

---

# 27. Common Production Problems

* Cache Stampede
* Cache Avalanche
* Cache Penetration
* Memory Exhaustion
* OOM Errors
* Replication Lag
* Failover Delays
* Network Latency
* Large Keys
* Hot Keys
* Slow Commands
* Fragmentation
* Cluster Rebalancing
* Connection Pool Exhaustion

---

# 28. Interview Focus Areas (Staff/Principal)

* Cache vs Database Trade-offs
* Redis Internal Architecture
* Data Structure Selection
* Cache Consistency Strategies
* Cache Invalidation Techniques
* Distributed Locking Trade-offs
* Redlock Limitations
* Persistence Trade-offs (RDB vs AOF)
* Redis Cluster Internals
* Sentinel vs Cluster
* Memory Optimization
* High Availability Design
* Scaling Strategy
* Performance Tuning
* Multi-region Cache Design
* Failure Recovery
* Capacity Planning
* Cost Optimization
* Spring Boot Integration
* Production Troubleshooting

---
