# Interview preparation — Spring Boot component with multiple databases

## Architecture & Design Patterns

1. You must implement a Spring Boot service that reads from a legacy relational database and writes to a new document store in the same user request. What design choices would you consider?

2. Your team considers using AbstractRoutingDataSource to route queries between databases by tenant or by operation type. What concerns and failure modes would you raise about routing correctness?

3. Consider a design that centralizes cross-database coordination via a message broker. What questions would you ask about ordering, at-least-once vs exactly-once delivery, transactional outbox, and exactly-once semantics?

15. When using different ORMs or data access technologies across databases (JPA for one, JDBC template for another), what approaches help unify error handling, transaction semantics, and resource cleanup?

29. When different databases have conflicting approaches to schema migrations and versioning, how would you approach migration orchestration, compatibility checks, and rolling deployments?

## Transactions & Consistency

2. A single use case requires updating two different databases atomically. How would you decide between using a distributed transaction (XA/2PC), a Saga pattern, or eventual consistency?

6. Describe a scenario where using separate TransactionManagers for each DataSource is necessary. What questions would you ask to ensure the correct TransactionManager is used at runtime?

9. When different databases use different consistency models (strong consistency vs eventual consistency), how would you design correct semantics across them?

10. Suppose DB-A supports XA and DB-B does not. How would you implement a safe two-phase workflow, including compensation steps, error handling, and operational complexity?

12. The component must adhere to strict isolation requirements for a financial operation that spans two databases. How would you approach isolation level choices, locking strategies, and preventing race conditions?

25. When implementing rollback behavior across databases, what do you know about rollback semantics for different TransactionManager implementations and designing compensating transactions?

26. The component supports a read-replica for reporting and an authoritative primary for writes. How would you ensure read-after-write correctness, cache invalidation, and replication lag handling?

27. Consider a design that centralizes cross-database coordination via a message broker. How would you handle ordering, delivery guarantees, and transactional outbox patterns?

39. Your Spring Boot application needs to coordinate writes across two databases within a single user transaction. Walk me through: (1) how @Transactional with Propagation.REQUIRED behaves across multiple TransactionManagers, (2) a failure scenario where DB-A commits but DB-B times out—what state do you recover to, (3) how Isolation.SERIALIZABLE on one database but READ_COMMITTED on another affects correctness when both must update related entities, and (4) what happens if one database's transaction is rolled back after a timeout but the other has already released locks.

## Failure Handling & Resilience

3. While integrating two databases, you observe frequent deadlocks when operations touch both databases in parallel. What scenarios would you test, and what strategies would you use to handle deadlocks?

4. Your component needs to perform a read from DB-A and an update in DB-B. Describe a scenario where partial failure occurs after DB-A is read but before DB-B is committed. What strategies would you use?

8. An operation must be retried on transient network failures when writing to one of the databases. How would you design retries considering idempotency, unique constraints, and duplicate prevention?

20. The system must support disaster recovery and failover across regions where replicas are read-only. How would you approach read/write routing, replication lag handling, and failover orchestration?

30. Present a stress scenario: full data center outage for DB-A while DB-B remains available. What would you do about degraded-mode operation, feature toggles, user experience, and recovery?

## Data Aggregation & Query Patterns

5. Your component needs to perform a read from a high-latency analytical DB and a low-latency OLTP DB in the same request. How would you design for different latency profiles?

28. For performance tuning, what query patterns span databases (e.g., fetching keys from one store then joining with another), batching strategies, and when to denormalize?

## Data Integrity & Migrations

11. You need to migrate part of the domain from one database to another while the system remains live. What stepwise approach would you take for data migration, dual-write strategy, and traffic shifting?

13. Design a scenario where schema changes in one database could break cross-database operations. What questions would you ask about backward/forward compatibility and safe rollout?

18. You discover conflicting uniqueness constraints between two data stores for the same business entity. What design approaches help with conflict detection and resolution?

## Concurrency & Ordering

17. A cross-database batch job must be interruptible and resumeable without duplicating work. How would you approach checkpointing, idempotent processing, and consistent commit boundaries?

21. A microservice receives a request that triggers parallel updates to three databases. How would you reason through ordering guarantees, partial failures, and consistent state?

40. Your Spring Boot service uses a traditional thread pool executor to coordinate writes to two databases in parallel. Scenario: (1) Thread T1 reads customer credit from DB-A, (2) Thread T2 computes discount from cache, (3) Both threads coordinate to write to DB-B. Walk through: what happens if T2 crashes before notifying T1, how do you detect this inconsistency, and when would Java 21 virtual threads improve this design by allowing 10,000 concurrent user sessions without thread-pool exhaustion? How does this change deadlock debugging?

41. Your team is evaluating migration from OS threads to Java 21 virtual threads for a high-concurrency Spring Boot service accessing multiple databases. Scenario: A batch job processes 1M records by spawning one virtual thread per record for parallel DB operations. Discuss: (1) how virtual thread scheduling differs from OS threads (no context-switch overhead, unmounting on blocking I/O), (2) how Spring's @Async and transaction handling adapt to this model, (3) whether connection pool sizing changes—should you increase pool size since threads no longer starve on I/O?, and (4) how to detect if a long-running transaction is still holding locks across multiple DB connections managed by virtual threads.

## Observability & Debugging

14. For observability and debugging, what would you ask about tracing, correlation IDs, transaction logs, and reconstructing cross-database flows when inconsistency is detected?

24. You need to monitor and alert on cross-database operational issues. How would you define useful SLOs, detect divergence between stores, and trigger automated mitigation?

## Testing

22. How would you test transactional behavior across multiple databases in unit, integration, and contract testing, including testcontainers and in-memory databases?

## Configuration & Resource Management

16. How would you configure connection pools and resource limits per DataSource so that high load on one database does not starve connections for the other?

## Long-Running Operations & Manual Intervention

23. If a long-running transaction spans multiple databases and a human operator may intervene, what would you discuss about timeouts, manual compensation, and safe operator workflows?

## Replication & Multi-Region Sync

32. How do primary and secondary replicas synchronize data, and what mechanisms ensure consistent data is served to clients across both replicas? What happens during network partitions?

33. In a multi-region cluster setup, how would you handle data synchronization across regions? What are the trade-offs between strong consistency, eventual consistency, and read-your-writes semantics?

34. How would you design failover from primary to secondary replica in a multi-region deployment? What are the data loss implications and how do you handle split-brain scenarios?

## Security & Access Control

19. When security and access controls differ between databases (different credentials, roles, or network zones), what approaches ensure secure configuration, least privilege, and audit trails?

35. Scenario: Your organization uses AWS IAM as the source of truth for user permissions. You need to provision database access for a newly promoted admin: (1) user's IAM role must be fetched and reconciled with database-side RBAC roles, (2) if IAM says "admin" but database says "read-only," which wins and why, (3) if provisioning to DB-A succeeds but DB-B times out, should you fail the entire user creation or allow partial access, (4) a user is terminated in IAM—how do you ensure all database access is revoked within 5 minutes across multi-region replicas, and (5) how do you audit which IAM role gave which database permission to catch privilege escalation attempts?

36. Your system manages secrets (database passwords, encryption keys, API credentials) that services need to access databases in multiple regions. Scenario: (1) How do you rotate a database password without downtime—do you read both old and new passwords during rotation, and for how long?, (2) if secret rotation fails mid-deployment (some instances got new password, others timed out), how do you detect and remediate partial state?, (3) a secret is compromised—do you invalidate all in-flight transactions or allow them to complete before revoking?, (4) in Java 21 virtual threads, how does holding a secret in memory for the lifetime of a thread affect security, and (5) how does mTLS certificate rotation in a high-concurrency service with 100k virtual threads affect connection pooling—do you need connection recycling?

37. Your Spring Boot service deployed with a load balancer routes requests across 5 instances to two databases (1 primary, 1 secondary replica). Scenario: (1) Request hits instance #3, reads from primary DB, then subsequent request hits instance #5—should this second request read from replica or primary to ensure read-after-write consistency?, (2) if you route based on geographic proximity (nearest region), what happens when replication lag is 5 seconds and user expects consistency?, (3) health checks detect primary is slow—how do you gracefully route new writes to primary but shift reads to replica without breaking transactions?, (4) during a load spike, the primary connection pool exhausts—should the load balancer retry to the same instance or failover to secondary, and what does "failover" mean for reads vs. writes?

38. In a multi-region deployment with firewall rules, you want to allow: database replication traffic between regions (high volume, must not bottleneck), application-to-database traffic (needs encryption), and monitoring queries (read-only, lower priority). Scenario: (1) Firewall rule allows TCP 3306 between regions—an attacker in one region attempts to connect to the primary database; how do you restrict this to replication traffic only?, (2) a DBA needs emergency access to query a prod database from their laptop in a different country—do you open the firewall rule temporarily (audit trail needed) or use a bastion host (adds latency), and (3) replication is lagging in a specific region because firewall MTU size mismatch causes packet fragmentation—how do you diagnose and fix this without rewriting rules?

## Deployment & Operational Changes

42. Your team is deploying a new version of the Spring Boot service that changes transaction propagation from Propagation.SUPPORTS to Propagation.REQUIRED. Scenario: (1) In-flight requests at deployment time are still running under the old code—do they continue to the end or are they interrupted?, (2) if you use rolling deployment (replace 1/5 instances at a time), what happens when an old instance calls a new instance's service and propagation behavior differs?, (3) the new version requires a new column in DB-B but not DB-A—how do you deploy without a coordination point that causes downtime?, (4) traffic is 500 requests/sec—during a 10-minute rolling deployment, you're running both old and new code; how do you ensure no transaction is half-committed (one DB upgraded, other not), and (5) if you need to rollback after 3 instances are updated, how do you recover transactions that were partially applied under the new code?

## Runtime Configuration & RBAC

31. You are designing an RBAC system where roles are stored in the database but cached on application startup for performance. An admin account is compromised; you must immediately revoke admin role and downgrade to read-only. You update the DB, but the compromised instance still has cached admin role. Scenario: (1) How do you push the cache invalidation to all running instances without restarting?, (2) if you publish an "admin revoked" event to a message queue, how long can you tolerate before all instances see it (5ms? 5s?), (3) what if the compromised instance hasn't consumed the invalidation message yet and tries to perform an admin action—do you block it or audit-log it?, (4) should you revoke all sessions of the user or allow existing sessions to complete, and (5) how do you ensure the cache invalidation is persisted so after a service restart, the admin role stays revoked?

## JVM Internals & Java 21

43. Explain the Java 21 virtual thread execution model in the context of Spring Boot multi-database operations: (1) when a virtual thread is blocked on a database read (waiting for network I/O), how does the JVM unmount it from a carrier (OS) thread and schedule other virtual threads, (2) if you have 100k virtual threads and a connection pool of 50 connections, what prevents thread starvation or deadlock when all threads are waiting on I/O, (3) in the old OS-thread model, a thread stack is 1-2MB; virtual threads have a heap-allocated stack that grows on demand—what are the GC implications when 100k threads exist in memory at once, (4) when a virtual thread is pinned (blocked on synchronized keyword or JNI), it cannot be unmounted—how does this affect Spring's transaction handling if @Transactional uses synchronized internally, and (5) how do you profile virtual thread performance when investigating a database bottleneck—what JVM flags or tools reveal which virtual threads are pinned or waiting?
