# Interview preparation — Spring Boot component with multiple databases

Below are scenario-based interview questions focused on designing Spring Boot components that interact with multiple databases, with emphasis on transaction separation, conflict handling, consistency, and operational concerns. Only questions are provided — no answers.

1. You must implement a Spring Boot service that reads from a legacy relational database and writes to a new document store in the same user request. Describe the design choices you would consider to ensure transactional consistency and how you'd structure the service to minimize coupling between the two persistence layers.

2. A single use case requires updating two different databases atomically. Explain, with scenarios, how you would decide between using a distributed transaction (XA/2PC), a Saga pattern, or eventual consistency, and what trade-offs each choice introduces.

3. While integrating two databases, you observe frequent deadlocks when operations touch both databases in parallel. What scenarios would you test to reproduce and reason about the deadlocks, and what design changes would you propose to avoid them at the component level?

4. Your component needs to perform a read from DB-A and an update in DB-B. Outline a scenario where a partial failure occurs after DB-A is read but before DB-B is committed. Which strategies would you put in place to detect and mitigate inconsistencies?

5. You are asked to expose a service that aggregates data from multiple databases with different latency profiles (one high-latency analytical DB, one low-latency OLTP DB). Propose scenario-based questions about caching, timeouts, and user-facing consistency guarantees you would evaluate.

6. Describe a scenario where using separate TransactionManagers for each DataSource is necessary. What questions would you ask to ensure the correct TransactionManager is used at runtime and to avoid accidental cross-database transactional assumptions?

7. Your team considers using AbstractRoutingDataSource to route queries between databases by tenant or by operation type. What scenario-based concerns and failure modes would you raise about routing correctness, transaction boundaries, and testing?

8. An operation must be retried on transient network failures when writing to one of the databases. Create scenario questions about idempotency, unique constraints, and how to design retries so that repeated attempts don't create conflicting state across databases.

9. When different databases use different consistency models (strong consistency vs eventual consistency), what interview scenarios would you present to evaluate a candidate's ability to design correct read-after-write behavior and user-visible anomalies?

10. Suppose DB-A supports XA and DB-B does not. Pose scenario-based questions to explore how you'd implement a safe two-phase workflow, including compensation steps, error handling, and the operational impact of partial failures.

11. You need to migrate part of the domain from one database to another while the system remains live. What stepwise scenarios would you ask about to validate data migration approach, dual-write strategies, verification, and rollback plans?

12. The component must adhere to strict isolation requirements for a financial operation that spans two databases. What scenarios would you propose to examine isolation level choices, locking strategies (optimistic vs pessimistic), and end-to-end correctness under concurrency?

13. Design a scenario where schema changes in one database could break cross-database operations. What questions would you ask about backward/forward compatibility, contract testing, and safe rollout approaches?

14. For observability and debugging, what scenario-based questions would you ask about tracing, correlation IDs, transaction logs, and how to reconstruct cross-database flows when an inconsistency is reported in production?

15. When using different ORMs or data access technologies across databases (JPA for one, JDBC template for another), which scenario questions help probe the candidate's approach to unifying error handling, transaction demarcation, and resource cleanup?

16. Propose scenarios that explore how to configure connection pools and resource limits per DataSource so that high load on one database does not starve connections for the other, and how to test those scenarios under stress.

17. A cross-database batch job must be interruptible and resumeable without duplicating work. What scenario questions would you ask about checkpointing, idempotent processing, and consistent commit boundaries across databases?

18. You discover conflicting uniqueness constraints between two data stores for the same business entity. What interview scenarios would surface design approaches for conflict detection, resolution strategies, and when to enforce a single source of truth.

19. When security and access controls differ between databases (different credentials, roles, or network zones), what scenarios would you present to evaluate secure configuration, least privilege, and secret management practices for the component?

20. The system must support disaster recovery and failover across regions where replicas are read-only. Create scenario-based questions that explore read/write routing, replication lag handling, and strategies to avoid serving stale or inconsistent data.

21. A microservice receives a request that triggers parallel updates to three databases. What scenarios would you ask about to reason through ordering guarantees, partial failures, and how the service should present outcome semantics to its callers?

22. Pose scenarios that evaluate how to test transactional behavior across multiple databases in unit, integration, and contract testing, including use of testcontainers, in-memory databases, and simulated network partitions.

23. If a long-running transaction spans multiple databases and a human operator may intervene, what scenario questions would you use to discuss timeouts, manual compensation, and safe operator workflows?

24. You need to monitor and alert on cross-database operational issues. What scenarios would you propose to define useful SLOs, detect divergence between stores, and trigger automated mitigation or manual investigation paths?

25. When implementing rollback behavior across databases, create scenario questions that probe knowledge about rollback semantics for different TransactionManager implementations, and how to design compensating actions where rollback is not global.

26. The component supports a read-replica for reporting and an authoritative primary for writes. What scenarios would you ask to evaluate read-after-write correctness assumptions, cache invalidation, and client-visible staleness under heavy write load?

27. Consider a design that centralizes cross-database coordination via a message broker. What scenario questions would you ask about ordering, at-least-once vs exactly-once delivery, transactional outbox patterns, and consumer-side deduplication?

28. For performance tuning, propose scenario questions that focus on query patterns that span databases (e.g., fetching keys from one store then joining with another), batching strategies, and when to denormalize data across stores.

29. When different databases have conflicting approaches to schema migrations and versioning, what interview scenarios would you present about migration orchestration, compatibility checks, and rolling back changes safely?

30. Finally, present a stress scenario: full data center outage for DB-A while DB-B remains available. What questions would you ask about degraded-mode operation, feature toggles, user experience, and re-synchronization after recovery?


/-- End of file --/
