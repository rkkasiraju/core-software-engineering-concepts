# Interview preparation — Spring Boot component with multiple databases

## Architecture & Design Patterns

1. You must implement a Spring Boot service that reads from a legacy relational database and writes to a new document store in the same user request. What design choices would you consider?

2. Your team considers using AbstractRoutingDataSource to route queries between databases by tenant or by operation type. What concerns and failure modes would you raise about routing correctness?

3. Consider a design that centralizes cross-database coordination via a message broker. What questions would you ask about ordering, at-least-once vs exactly-once delivery, transactional outbox, and exactly-once semantics?

15. When using different ORMs or data access technologies across databases (JPA for one, JDBC template for another), what approaches help unify error handling, transaction semantics, and resource cleanup?

29. When different databases have conflicting approaches to schema migrations and versioning, how would you approach migration orchestration, compatibility checks, and rolling deployments?

63. Your team needs cross-database synchronization between relational, document, and event stores. Would you build a custom synchronization framework or adopt an existing platform? Walk through evaluation criteria, operational complexity, vendor lock-in, scalability, cost, and long-term maintenance.

72. Your system has grown from a monolith to 200+ services, and development velocity has slowed significantly. How would you identify architectural bottlenecks (service boundary mismatches, excessive inter-service calls, shared state, deployment coordination overhead) and evolve the system?

73. A business acquisition requires integrating two completely different platforms within six months. How would you approach architecture (data model reconciliation, API contract negotiation, team autonomy), migration strategy (phased vs big bang, rollback procedures), and risk reduction (feature flag isolation, separate deployments)?

74. A critical third-party vendor announces end-of-life for a platform your organization depends on. How would you plan the replacement (build vs buy vs alternative vendor), manage dual-running systems, coordinate team capacity, and minimize disruption?

75. Different teams have adopted different technologies for solving the same problem (microservice frameworks, database choices, cache backends). How would you standardize without disrupting delivery (consensus building, migration paths, cost/risk analysis)?

76. The organization wants to migrate from on-premises to cloud while continuing feature development. How would you approach the migration (data replication, network connectivity, failover/failback, compliance, cost management)?

## Scalability

77. Your application suddenly experiences 20× normal traffic after a product launch. Walk through: (1) identifying bottlenecks (database, application, network, storage), (2) scaling synchronously vs queuing requests, (3) load testing to validate capacity increases, (4) graceful degradation strategies, and (5) cost vs latency trade-offs.

78. One customer generates 80% of the platform traffic, affecting every other tenant (noisy neighbor problem). How would you redesign the system (per-customer connection pools, traffic shaping, workload isolation, tiered SLOs)?

79. Traffic grows gradually over two years until latency becomes unacceptable. How would you determine whether to optimize existing code (low-hanging fruit), redesign components (replication, sharding), or architect fundamentally differently (microservices)?

80. Your APIs handle millions of requests per minute, but only a few endpoints become bottlenecks. How would you investigate (distributed tracing, database query analysis, dependency profiling) and implement targeted fixes (caching, async processing, circuit breakers)?

81. Storage requirements increase by 100 TB every year. How would you redesign storage architecture (tiering hot/warm/cold data, data retention policies, compression, archival strategies)?

## Production Incidents

82. Customers report missing data, but all dashboards show the system is healthy. How would you investigate (data consistency checks across databases, audit logs, eventual consistency windows, replay gaps in event streams)?

83. Multiple services fail simultaneously after a routine deployment. How would you coordinate incident response (blast radius assessment, deployment rollback decision, service restoration priority, incident timeline reconstruction)?

84. Production latency increases every day at exactly the same time. How would you investigate (scheduled batch jobs, cache expiration cycles, cron maintenance tasks, external service degradation at fixed times)?

85. CPU utilization remains low while request latency increases significantly. What possibilities would you explore (connection pool exhaustion, lock contention, I/O bottlenecks, garbage collection pauses, downstream service slowdown)?

86. Users intermittently receive stale data even though databases are healthy. How would you debug the issue (read-after-write consistency gaps, eventual consistency windows, cache invalidation bugs, clock skew across nodes)?

## Distributed Systems

87. Two services disagree about the current state of the same business entity. How would you determine which state is correct (event log replay, authoritative system identification, eventual consistency reconciliation, idempotency key verification)?

88. A distributed workflow completes successfully for 99.9% of requests but occasionally leaves inconsistent data. How would you investigate (race conditions in saga coordination, timeout edge cases, idempotency failures, compensating transaction bugs)?

89. Events begin arriving out of order after scaling consumers horizontally. How would you redesign processing (per-partition ordering enforcement, causality tracking with version vectors, replay mechanisms)?

90. A message queue accumulates millions of unprocessed events overnight. How would you recover safely (detecting root cause of stall, restarting consumers without duplicate processing, prioritizing critical events, capacity planning)?

91. Different services independently retry failed requests, creating exponential traffic amplification. How would you prevent cascading failures (exponential backoff with jitter, circuit breakers, bulkheads, request deduplication)?

## Database

92. Database CPU reaches 100% while application servers remain mostly idle. How would you identify the root cause (slow queries, missing indexes, table scans on large datasets, lock contention, connection pool misuse)?

93. Read replicas begin returning stale data during peak traffic. How would you maintain correctness (read-your-writes consistency, read-from-primary fallback, consistency level negotiation, replication lag monitoring)?

94. A schema migration must be performed without downtime on a database serving millions of users. How would you execute it (backward compatibility windows, shadow columns, zero-downtime deployment patterns)?

95. One database shard grows much faster than the others. How would you rebalance the system (resharding strategy, data migration coordination, temporary hotspot handling)?

96. A production index is accidentally dropped during business hours. How would you recover while minimizing customer impact (recreate index with minimal locking, query plan degradation management, customer communication)?

## Concurrency

97. Duplicate financial transactions occasionally occur under heavy load. How would you investigate (race condition detection, idempotency key missing, database uniqueness constraint timing, transaction isolation level analysis)?

98. Two users simultaneously modify the same business object and both updates succeed incorrectly. How would you redesign consistency (optimistic locking with version numbers, pessimistic locking, CAS operations, conflict resolution)?

99. Deadlocks begin increasing after introducing parallel processing. How would you identify the root cause (lock ordering violations, query plan changes, contention visualization, automated detection)?

100. Thousands of concurrent operations compete for the same shared resource. How would you reduce contention (lock-free data structures, batching, striped locks, resource pooling)?

101. Batch jobs overlap unexpectedly and process the same records twice. How would you prevent duplicate work (distributed locks, idempotent processing, job deduplication tracking)?

## Performance

102. Average latency is acceptable, but P99 latency continues increasing. How would you investigate (long-tail distribution sources, outlier queries, GC pauses, virtual thread starvation)?

103. A new release doubles memory usage without increasing functionality. How would you analyze the regression (heap dump analysis, object allocation profiling, memory leak detection)?

104. Throughput decreases as additional application instances are added. What possibilities would you investigate (shared bottleneck, contention, work stealing, uneven load distribution)?

105. Garbage collection pauses become unpredictable after increasing heap size. How would you tune the application (GC algorithm selection, heap region sizing, object allocation patterns)?

106. Network utilization appears normal, yet user experience is poor. How would you investigate (packet loss, latency spikes, DNS resolution delays, load balancer issues)?

## Caching

107. Cache hit ratio suddenly drops after deployment. How would you determine the cause (data eviction policy changes, TTL reduction, cache key format modification, traffic pattern shift)?

108. Cache invalidation occasionally fails, causing inconsistent customer experiences. How would you redesign the solution (event-driven invalidation, time-based expiration with staggering, cache versioning)?

109. Cache servers fail during peak traffic. How should the application behave (graceful degradation, cache bypass, circuit breaker activation, queue upstream requests)?

110. A cache warm-up process overloads the database after every deployment. How would you improve it (async warm-up, staged loading, resource throttling)?

111. Multiple services maintain independent caches for the same data. How would you ensure consistency (distributed cache, invalidation messaging, TTL coordination)?

## Kubernetes & Platform

112. Kubernetes repeatedly restarts healthy application pods. How would you investigate (readiness probe false positives, liveness probe sensitivity, resource limit thrashing, kernel OOM killer)?

113. Autoscaling adds more pods, but throughput does not improve. What possibilities would you explore (resource bottleneck elsewhere, connection pool saturation, licensing limits, fixed-size shared resources)?

114. A cluster upgrade unexpectedly impacts production traffic. How would you minimize risk (canary upgrades, drain verification, version compatibility testing)?

115. Resource utilization appears low while pods frequently fail due to resource limits. How would you diagnose the issue (memory spikes, burstable workloads, uneven distribution)?

116. Node failures occur during peak business hours. How should workloads recover (pod affinity policies, graceful drain coordination, failover speed)?

## Networking

117. Users in one geographic region experience significantly higher latency than others. How would you investigate (CDN coverage, regional cloud availability, DNS routing, network topology)?

118. API calls intermittently fail between services while infrastructure dashboards appear healthy. What would you examine (network jitter, DNS flakiness, SSL handshake timeouts, load balancer connection limits)?

119. DNS changes cause intermittent outages after deployment. How would you diagnose the issue (TTL propagation delays, DNS caching conflicts, connection reuse)?

120. TLS certificate renewal unexpectedly breaks service communication. How would you prevent this (automation with verification, certificate rotation scheduling, monitoring)?

121. Network partitions isolate one data center from the rest of the system. How should the application behave (split-brain prevention, quorum-based decisions, data consistency trade-offs)?

## Security

122. An application credential is accidentally exposed publicly. Walk through your response: (1) credential rotation within minutes, (2) detecting whether the credential was used, (3) active connection invalidation, (4) secret propagation to all instances, (5) audit trail analysis, (6) incident communication, (7) post-incident prevention measures.

123. Unauthorized data access is detected several weeks after deployment. How would you investigate (audit log analysis, timeline reconstruction, scope of breach assessment, regulatory notification requirements)?

124. A security vulnerability affects a widely used library across hundreds of services. How would you coordinate remediation (dependency mapping, prioritization, rolling patch deployment, verification)?

125. A privileged employee account is compromised. How would you limit business impact (immediate credential revocation, session termination, audit log review, access pattern analysis)?

126. Your organization adopts Zero Trust networking. What architectural changes become necessary (identity verification for every connection, certificate-based auth, encryption in transit, network segmentation)?

## CI/CD & Deployment

127. A deployment succeeds technically but introduces subtle business inconsistencies. How would you detect them early (contract testing, data consistency checks, canary validation, automated rollback triggers)?

128. Rolling deployment leaves old and new versions communicating incorrectly. How would you avoid compatibility issues (API versioning, backward compatibility windows, coordinated schema changes)?

129. A rollback restores application code but not database changes. How would you recover (schema rollback procedures, dual-write strategies, data reconciliation)?

130. Different environments drift significantly over time. How would you restore consistency (infrastructure-as-code enforcement, automated drift detection, compliance scanning)?

131. Feature flags accidentally expose unfinished functionality to customers. How would you improve release safety (flag lifecycle enforcement, automated cleanup, access control)?

## Reliability Engineering

132. A dependency slows down but never completely fails. How should your application respond (timeout boundaries, adaptive retry, circuit breaker thresholds, fallback logic)?

133. Retry mechanisms intended to improve reliability instead overload downstream systems. How would you redesign them (exponential backoff, jitter, rate limiting, idempotency requirements)?

134. Circuit breakers frequently oscillate between open and closed states. What tuning considerations would you make (half-open duration, recovery threshold, consecutive failure counting)?

135. A regional outage requires failover, but replicated data is several minutes behind. How would you make business decisions (RPO/RTO trade-offs, data loss acceptance, consistency vs availability)?

136. A disaster recovery exercise reveals recovery objectives cannot be met. How would you improve preparedness (capacity planning, backup frequency, failover automation)?

## Observability

137. Customers report issues that cannot be reproduced in lower environments. How would you improve observability (production telemetry, user session replay, canary deployments)?

138. Every service logs independently, making incident reconstruction difficult. How would you redesign observability (centralized logging, trace correlation, unified query language)?

139. Monitoring generates thousands of alerts during a single outage. How would you reduce alert fatigue (alert aggregation, severity clustering, intelligent deduplication)?

140. Metrics show healthy infrastructure while business KPIs decline. What additional telemetry would you collect (application-level metrics, user journey tracking, revenue impact measurement)?

141. A critical production issue leaves almost no logs because logging was rate-limited. How would you redesign diagnostics (adaptive sampling, priority-based retention, structured logging)?

## Leadership & Decision Making

142. Two engineering teams strongly disagree on architectural direction. How would you facilitate the decision (evidence gathering, prototype comparison, risk assessment, consensus building)?

143. A critical project is falling behind because of dependencies across multiple teams. How would you regain momentum (dependency mapping, parallel workstream creation, unblocking strategies)?

144. Leadership requests delivery in half the estimated time. How would you respond (scope negotiation, quality/speed trade-offs, risk quantification, alternative timelines)?

145. A production incident occurs while senior engineers are unavailable. How would you lead the response (escalation decision, on-call coordination, confidence building, decision authority)?

146. Multiple stakeholders prioritize conflicting business objectives. How would you drive alignment (data-driven prioritization, impact assessment, phased delivery)?

## AI & Emerging Technologies

147. An AI assistant begins producing incorrect business recommendations after a model update. How would you investigate (model performance regression, data drift detection, inference pipeline validation)?

148. A Retrieval-Augmented Generation (RAG) system returns outdated information despite recent updates. How would you diagnose retrieval quality (embedding staleness, ranking algorithm issues, knowledge base inconsistency)?

149. AI inference costs increase 5× in one month. How would you optimize architecture without reducing quality (batching, caching, quantization, model selection)?

150. Autonomous agents begin repeatedly calling one another, creating an execution loop. How would you detect and prevent it (call graph analysis, recursion depth limits, conversation history analysis)?

151. Regulations require explaining every AI-generated decision. How would you design for explainability, auditability, and compliance (feature attribution, decision logging, human override capabilities)?

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

47. Three independent microservices own Customer, Orders, and Billing databases. A customer deletion request must propagate safely across all services. Walk through saga orchestration vs choreography, timeout handling, compensation, retry storms, and operational monitoring.

## Failure Handling & Resilience

3. While integrating two databases, you observe frequent deadlocks when operations touch both databases in parallel. What scenarios would you test, and what strategies would you use to handle deadlocks?

4. Your component needs to perform a read from DB-A and an update in DB-B. Describe a scenario where partial failure occurs after DB-A is read but before DB-B is committed. What strategies would you use?

8. An operation must be retried on transient network failures when writing to one of the databases. How would you design retries considering idempotency, unique constraints, and duplicate prevention?

20. The system must support disaster recovery and failover across regions where replicas are read-only. How would you approach read/write routing, replication lag handling, and failover orchestration?

30. Present a stress scenario: full data center outage for DB-A while DB-B remains available. What would you do about degraded-mode operation, feature toggles, user experience, and recovery?

57. Database latency increases by only 500ms, yet every downstream service begins timing out within minutes. Explain how thread pools, retries, circuit breakers, connection pools, queues, and load balancers interact to create cascading failures and how you would stop them.

58. You intentionally inject packet loss between the application and one database during a chaos experiment. What behavior would you expect, which resilience mechanisms should activate, and how would you determine whether the experiment succeeded?

## Data Aggregation & Query Patterns

5. Your component needs to perform a read from a high-latency analytical DB and a low-latency OLTP DB in the same request. How would you design for different latency profiles?

28. For performance tuning, what query patterns span databases (e.g., fetching keys from one store then joining with another), batching strategies, and when to denormalize?

## Data Integrity & Migrations

11. You need to migrate part of the domain from one database to another while the system remains live. What stepwise approach would you take for data migration, dual-write strategy, and traffic shifting?

13. Design a scenario where schema changes in one database could break cross-database operations. What questions would you ask about backward/forward compatibility and safe rollout?

18. You discover conflicting uniqueness constraints between two data stores for the same business entity. What design approaches help with conflict detection and resolution?

59. Your system relies on Change Data Capture to synchronize two databases. CDC processing stops for several hours due to connector failure. How would you detect missing events, recover safely, reconcile data divergence, and avoid duplicate processing?

65. A 15-year-old monolithic application using a single Oracle database is gradually migrating to microservices with PostgreSQL, Kafka, and MongoDB. How would you design the migration strategy, minimize downtime, avoid data inconsistencies, phase traffic, and determine when the legacy database can finally be retired?

## Concurrency & Ordering

17. A cross-database batch job must be interruptible and resumeable without duplicating work. How would you approach checkpointing, idempotent processing, and consistent commit boundaries?

21. A microservice receives a request that triggers parallel updates to three databases. How would you reason through ordering guarantees, partial failures, and consistent state?

40. Your Spring Boot service uses a traditional thread pool executor to coordinate writes to two databases in parallel. Scenario: (1) Thread T1 reads customer credit from DB-A, (2) Thread T2 computes discount from cache, (3) Both threads coordinate to write to DB-B. Walk through: what happens if T2 crashes before notifying T1, how do you detect this inconsistency, and when would Java 21 virtual threads improve this design by allowing 10,000 concurrent user sessions without thread-pool exhaustion? How does this change deadlock debugging?

41. Your team is evaluating migration from OS threads to Java 21 virtual threads for a high-concurrency Spring Boot service accessing multiple databases. Scenario: A batch job processes 1M records by spawning one virtual thread per record for parallel DB operations. Discuss: (1) how virtual thread scheduling differs from OS threads (no context-switch overhead, unmounting on blocking I/O), (2) how Spring's @Async and transaction handling adapt to this model, (3) whether connection pool sizing changes—should you increase pool size since threads no longer starve on I/O?, and (4) how to detect if a long-running transaction is still holding locks across multiple DB connections managed by virtual threads.

46. Your service publishes customer events to Kafka after writing to DB-A while another service updates DB-B based on those events. A partition rebalance occurs during processing. How would you reason about ordering guarantees, duplicate delivery, replay safety, idempotent consumers, and reconciliation?

## Observability & Debugging

14. For observability and debugging, what would you ask about tracing, correlation IDs, transaction logs, and reconstructing cross-database flows when inconsistency is detected?

24. You need to monitor and alert on cross-database operational issues. How would you define useful SLOs, detect divergence between stores, and trigger automated mitigation?

49. A production incident shows inconsistent data between two databases, but distributed tracing is incomplete because one service failed to propagate the trace context. How would you reconstruct the execution path using logs, metrics, database audit records, and message IDs?

50. An engineer adds customerId as a Prometheus label causing millions of unique time series and monitoring instability. How would you detect the issue, redesign metrics, preserve observability, and prevent similar incidents?

## Testing

22. How would you test transactional behavior across multiple databases in unit, integration, and contract testing, including testcontainers and in-memory databases?

## Configuration & Resource Management

16. How would you configure connection pools and resource limits per DataSource so that high load on one database does not starve connections for the other?

45. A sudden traffic spike causes DB-A's connection pool to become exhausted while DB-B still has available connections. How would you identify the bottleneck, prevent cascading failures, configure pool isolation, and recover without restarting the service?

## Long-Running Operations & Manual Intervention

23. If a long-running transaction spans multiple databases and a human operator may intervene, what would you discuss about timeouts, manual compensation, and safe operator workflows?

## Replication & Multi-Region Sync

32. How do primary and secondary replicas synchronize data, and what mechanisms ensure consistent data is served to clients across both replicas? What happens during network partitions?

33. In a multi-region cluster setup, how would you handle data synchronization across regions? What are the trade-offs between strong consistency, eventual consistency, and read-your-writes semantics?

34. How would you design failover from primary to secondary replica in a multi-region deployment? What are the data loss implications and how do you handle split-brain scenarios?

## Caching

48. Your application uses Redis to cache data originating from DB-A. During regional failover, DB-A switches to another primary while Redis still contains stale values. How would you detect stale cache, invalidate safely, prevent cache stampede, and ensure read-after-write consistency?

## Security & Access Control

19. When security and access controls differ between databases (different credentials, roles, or network zones), what approaches ensure secure configuration, least privilege, and audit trails?

35. Scenario: Your organization uses AWS IAM as the source of truth for user permissions. You need to provision database access for a newly promoted admin: (1) user's IAM role must be fetched and reconciled with database-side RBAC roles, (2) if IAM says "admin" but database says "read-only," which wins and why, (3) if provisioning to DB-A succeeds but DB-B times out, should you fail the entire user creation or allow partial access, (4) a user is terminated in IAM—how do you ensure all database access is revoked within 5 minutes across multi-region replicas, and (5) how do you audit which IAM role gave which database permission to catch privilege escalation attempts?

36. Your system manages secrets (database passwords, encryption keys, API credentials) that services need to access databases in multiple regions. Scenario: (1) How do you rotate a database password without downtime—do you read both old and new passwords during rotation, and for how long?, (2) if secret rotation fails mid-deployment (some instances got new password, others timed out), how do you detect and remediate partial state?, (3) a secret is compromised—do you invalidate all in-flight transactions or allow them to complete before revoking?, (4) in Java 21 virtual threads, how does holding a secret in memory for the lifetime of a thread affect security, and (5) how does mTLS certificate rotation in a high-concurrency service with 100k virtual threads affect connection pooling—do you need connection recycling?

37. Your Spring Boot service deployed with a load balancer routes requests across 5 instances to two databases (1 primary, 1 secondary replica). Scenario: (1) Request hits instance #3, reads from primary DB, then subsequent request hits instance #5—should this second request read from replica or primary to ensure read-after-write consistency?, (2) if you route based on geographic proximity (nearest region), what happens when replication lag is 5 seconds and user expects consistency?, (3) health checks detect primary is slow—how do you gracefully route new writes to primary but shift reads to replica without breaking transactions?, (4) during a load spike, the primary connection pool exhausts—should the load balancer retry to the same instance or failover to secondary, and what does "failover" mean for reads vs. writes?

38. In a multi-region deployment with firewall rules, you want to allow: database replication traffic between regions (high volume, must not bottleneck), application-to-database traffic (needs encryption), and monitoring queries (read-only, lower priority). Scenario: (1) Firewall rule allows TCP 3306 between regions—an attacker in one region attempts to connect to the primary database; how do you restrict this to replication traffic only?, (2) a DBA needs emergency access to query a prod database from their laptop in a different country—do you open the firewall rule temporarily (audit trail needed) or use a bastion host (adds latency), and (3) replication is lagging in a specific region because firewall MTU size mismatch causes packet fragmentation—how do you diagnose and fix this without rewriting rules?

53. Your organization adopts a Zero Trust model where every service-to-database connection requires identity verification and short-lived credentials. How would you redesign authentication, certificate rotation, authorization, audit logging, and operational recovery?

54. A production database credential is accidentally committed to a public repository. Describe the first hour of your response: credential rotation, active connection handling, secret propagation, audit investigation, incident communication, and post-incident improvements.

## Deployment & Operational Changes

42. Your team is deploying a new version of the Spring Boot service that changes transaction propagation from Propagation.SUPPORTS to Propagation.REQUIRED. Scenario: (1) In-flight requests at deployment time are still running under the old code—do they continue to the end or are they interrupted?, (2) if you use rolling deployment (replace 1/5 instances at a time), what happens when an old instance calls a new instance's service and propagation behavior differs?, (3) the new version requires a new column in DB-B but not DB-A—how do you deploy without a coordination point that causes downtime?, (4) traffic is 500 requests/sec—during a 10-minute rolling deployment, you're running both old and new code; how do you ensure no transaction is half-committed (one DB upgraded, other not), and (5) if you need to rollback after 3 instances are updated, how do you recover transactions that were partially applied under the new code?

44. Your Spring Boot service is processing a cross-database transaction when Kubernetes decides to evict the pod due to node maintenance. Walk through: (1) what happens to in-flight transactions, (2) how do readiness/liveness probes affect draining, (3) how do you avoid duplicate processing after the pod restarts, (4) how do you coordinate graceful shutdown with transaction completion, and (5) what operational metrics indicate unsafe termination?

55. A canary deployment introduces a transaction bug affecting only 5% of traffic. How would you detect it quickly, define rollback thresholds, prevent inconsistent cross-database writes, and verify recovery before resuming rollout?

56. Your GitOps repository declares one database configuration while production clusters have manual changes. How would you detect configuration drift, reconcile safely, prevent unauthorized modifications, and validate consistency across environments?

## Runtime Configuration & RBAC

31. You are designing an RBAC system where roles are stored in the database but cached on application startup for performance. An admin account is compromised; you must immediately revoke admin role and downgrade to read-only. Scenario: (1) How do you push the cache invalidation to all running instances without restarting?, (2) if you publish an "admin revoked" event to a message queue, how long can you tolerate before all instances see it (5ms? 5s?)?, (3) what if the compromised instance hasn't consumed the invalidation message yet and tries to perform an admin action—do you block it or audit-log it?, (4) should you revoke all sessions of the user or allow existing sessions to complete, and (5) how do you ensure the cache invalidation is persisted so after a service restart, the admin role stays revoked?

## JVM Internals & Java 21

43. Explain the Java 21 virtual thread execution model in the context of Spring Boot multi-database operations: (1) when a virtual thread is blocked on a database read (waiting for network I/O), how does the JVM unmount it from a carrier (OS) thread and schedule other virtual threads, (2) if you have 100k virtual threads and a connection pool of 50 connections, what prevents thread starvation or deadlock when all threads are waiting on I/O, (3) in the old OS-thread model, a thread stack is 1-2MB; virtual threads have a heap-allocated stack that grows on demand—what are the GC implications when 100k threads exist in memory at once, (4) when a virtual thread is pinned (blocked on synchronized keyword or JNI), it cannot be unmounted—how does this affect Spring's transaction handling if @Transactional uses synchronized internally, and (5) how do you profile virtual thread performance when investigating a database bottleneck—what JVM flags or tools reveal which virtual threads are pinned or waiting?

## Performance Engineering

51. Average latency remains below 50ms, but P99 latency exceeds 4 seconds during peak load. How would you determine whether the bottleneck is thread scheduling, connection pools, garbage collection, database locks, network latency, or downstream services?

52. Following a deployment, JVM pauses increase significantly while processing concurrent database requests. Walk through how you would investigate heap growth, object allocation, virtual thread behavior, GC tuning, and safe production rollout.

## Core Java Concurrency Scenarios

66. A Spring Boot service defines a static HashMap to cache database query results. The cache is populated during class initialization. Scenario: (1) Multiple threads concurrently access this cache in read-heavy workload—what visibility and atomicity issues could arise, (2) if thread T1 reads from the cache while thread T2 is modifying it, what can T1 observe (stale data, partial updates, exceptions)?, (3) how does this differ when a non-static instance field is used instead, and thread-local storage is involved?, (4) if you replace HashMap with ConcurrentHashMap, what guarantees change regarding iteration consistency and lock-free reads, and (5) how does this scenario change if the cache is accessed within a @Transactional method where the transaction must be isolated per thread?

67. A @Async method in a Spring Boot service submits database tasks to an ExecutorService thread pool. Scenario: (1) The thread pool has size 10 but 20 concurrent @Async calls arrive—what happens to the queued tasks, thread creation, and rejection policy?, (2) if a thread T1 holds a database connection and exception is thrown in @Async task, how does Spring's transaction management handle rollback (will it rollback or leak the connection)?, (3) thread-local variables like TransactionContext are used—are they propagated to @Async threads or are they null, and what are the implications?, (4) if the main thread waits for all @Async tasks to complete but never calls executor.shutdown(), what resource leaks occur and how does this affect multi-threaded database operations, and (5) how does CompletableFuture.supplyAsync() differ from @Async when coordinating cross-database writes?

68. A static volatile boolean flag is used to signal graceful shutdown of a long-running batch job that updates two databases. Scenario: (1) Thread T1 is mid-transaction on DB-A while T2 sets shutdownFlag = true—should T1 commit or rollback, and how do you coordinate this?, (2) if shutdownFlag is not volatile but just a regular boolean, what visibility guarantees are lost in a multi-threaded JVM, and how long can T1 miss the shutdown signal?, (3) a deadlock occurs between T1 (waiting for DB response) and T2 (trying to set the flag)—how would you detect this and prevent it?, (4) if 100 virtual threads are running the batch job and the flag is set, how do you ensure all 100 threads see the shutdown within 100ms and drain gracefully, and (5) how does this differ when using an AtomicBoolean vs volatile boolean in terms of happens-before semantics?

69. A static final reference to a Spring-managed database connection pool is initialized once in a static block. Scenario: (1) What visibility and ordering guarantees does static final provide when the static block reads configuration files?, (2) if the static block throws an exception, what happens to subsequent class usage—will the class be unusable forever?, (3) if two ClassLoaders load this class separately, do they share the same static pool instance or have separate instances, and how does this affect transaction isolation in a multi-tenant application?, (4) a developer modifies the connection pool configuration in the static block after deployment—they recompile but forget to restart the service; why does the change not take effect (explain class initialization timing), and (5) how does this scenario differ when using Spring's @Configuration and @Bean instead of a static block, and what are the thread-safety implications?

70. A non-synchronized method updateBalance() reads from a static balance field, computes a new value, and writes it back. This method is called by 100 virtual threads concurrently. Scenario: (1) What is a race condition in this context, and what values could the balance field hold after all 100 threads complete?, (2) if you add synchronized to the method, what is the performance cost in a high-concurrency scenario with Java 21 virtual threads (will it cause pinning)?, (3) if each thread increments balance by 1, starting from 0, but there are data races, what is the range of possible final values, and is it always less than 100?, (4) how does using AtomicLong.incrementAndGet() solve this, and what is the GC impact when 100k virtual threads use AtomicLong operations, and (5) if this method is invoked from two separate Spring Boot instances (distributed), does synchronized provide consistency across instances, and what distributed coordination mechanism would you use?

71. A Spring Boot service defines a thread-local variable to store the current user context. Scenario: (1) A request thread T1 sets the thread-local with User{id=123}, calls @Async method that updates DB-A, which submits another @Async to update DB-B—what is the user context in each thread (T2, T3)?, (2) if the servlet thread pool reuses thread T1 for a new request with User{id=456}, but the thread-local still contains User{id=123} from the previous request, what is the impact on database operations, and how do you prevent this leak?, (3) if you use InheritableThreadLocal instead of ThreadLocal in a virtual thread context, what happens when the JVM pools and reuses carrier threads, and is the user context inherited correctly?, (4) how does Spring's RequestContextHolder use thread-locals to store SecurityContext, and what happens when this request context crosses service boundaries (gRPC, HTTP to another service) without propagation?, and (5) if 100k virtual threads use thread-local storage, what is the memory overhead compared to 10 OS threads with the same thread-locals?

## AI-Assisted Operations

60. Your organization introduces an AI assistant capable of generating SQL queries for support engineers. How would you prevent unsafe queries, enforce RBAC, validate generated SQL, audit execution, and avoid accidental production data modification?

## Cost Optimization

61. Monthly cloud costs double after enabling cross-region replication and increased database throughput. How would you identify the primary contributors, evaluate architecture trade-offs, optimize costs, and ensure reliability is not compromised?

## Governance & Compliance

62. A customer requests complete data deletion, but their information exists across multiple databases, caches, backups, analytics systems, and event logs. How would you design deletion workflows while maintaining legal compliance, auditability, and operational safety?

## Leadership & Incident Management

64. At 2 AM, a production incident causes inconsistent financial data across two databases affecting thousands of users. As the technical lead, explain how you coordinate engineers, communicate with executives, prioritize recovery, decide whether to rollback, and conduct the postmortem.
