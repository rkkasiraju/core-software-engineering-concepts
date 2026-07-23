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

## Observability & Debugging

14. For observability and debugging, what would you ask about tracing, correlation IDs, transaction logs, and reconstructing cross-database flows when inconsistency is detected?

24. You need to monitor and alert on cross-database operational issues. How would you define useful SLOs, detect divergence between stores, and trigger automated mitigation?

## Testing

22. How would you test transactional behavior across multiple databases in unit, integration, and contract testing, including testcontainers and in-memory databases?

## Configuration & Resource Management

16. How would you configure connection pools and resource limits per DataSource so that high load on one database does not starve connections for the other?

## Long-Running Operations & Manual Intervention

23. If a long-running transaction spans multiple databases and a human operator may intervene, what would you discuss about timeouts, manual compensation, and safe operator workflows?

## Security & Access Control

19. When security and access controls differ between databases (different credentials, roles, or network zones), what approaches ensure secure configuration, least privilege, and audit trails?

## RBAC & Runtime Configuration Cache Invalidation

31. You are designing an RBAC system where roles are stored in the database but cached on application startup for performance. An admin account is compromised and becomes suspicious; you need to immediately revoke its admin role and downgrade it to read-only access to mitigate damage. You update the DB to reflect this change, but the compromised instance still has the cached admin role in memory. How do you handle the rest of the running application instances to ensure the permission change is enforced immediately across the entire system?
