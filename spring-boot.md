# 1. Spring Ecosystem Overview

* Spring Framework
* Spring Boot
* Spring Data
* Spring Security
* Spring Cloud
* Spring Integration
* Spring Batch
* Spring AI (high level)
* Spring Modulith

---

# 2. Bootstrapping

* Spring Initializr
* Starter Dependencies
* Auto Configuration
* Embedded Servers
* Fat JAR
* Native Image (GraalVM)
* AOT Processing

---

# 3. IoC & Dependency Injection

* IoC Container
* BeanFactory
* ApplicationContext
* Dependency Injection
* Constructor Injection
* Setter Injection
* Field Injection
* Bean Scopes
* Bean Naming
* Lazy Initialization

---

# 4. Bean Lifecycle

* Bean Creation
* Dependency Resolution
* Initialization
* @PostConstruct
* InitializingBean
* BeanPostProcessor
* BeanFactoryPostProcessor
* SmartInitializingSingleton
* DisposableBean
* @PreDestroy

---

# 5. Configuration

* @Configuration
* @Bean
* @Component
* @ComponentScan
* @Import
* @ImportResource
* Conditional Beans
* Profiles
* Externalized Configuration
* Property Binding
* Configuration Properties
* YAML
* Environment
* Property Sources

---

# 6. Component Stereotypes

* @Component
* @Service
* @Repository
* @Controller
* @RestController

---

# 7. Spring Boot Auto Configuration

* @EnableAutoConfiguration
* AutoConfiguration.imports
* Conditional Annotations
* Custom Auto Configuration
* Exclusions
* Starter Creation

---

# 8. REST APIs

* Controllers
* Request Mapping
* HTTP Methods
* Path Variables
* Request Parameters
* Request Body
* ResponseEntity
* Content Negotiation
* File Upload
* File Download
* Multipart Support

---

# 9. Validation

* Jakarta Validation
* Bean Validation
* Custom Validators
* Validation Groups
* Nested Validation

---

# 10. Exception Handling

* @ExceptionHandler
* @ControllerAdvice
* @RestControllerAdvice
* Problem Details (RFC 9457)
* Global Exception Handling
* Custom Exceptions

---

# 11. Serialization

* Jackson
* JSON Views
* Custom Serializers
* Custom Deserializers
* ObjectMapper
* Date Handling

---

# 12. Spring Data

* Repository Pattern
* CrudRepository
* JpaRepository
* PagingAndSortingRepository
* Query Methods
* Specifications
* QueryDSL
* Auditing
* Projections

---

# 13. Hibernate & JPA

* Entity Lifecycle
* Persistence Context
* Dirty Checking
* Flush
* Entity States
* Lazy Loading
* Eager Loading
* Fetch Join
* Cascade
* Orphan Removal
* Locking
* Transactions
* Entity Graph
* N+1 Problem

---

# 14. Transactions

* @Transactional
* Propagation
* Isolation
* Rollback Rules
* Read Only Transactions
* Nested Transactions
* Multiple Transaction Managers
* Distributed Transactions
* Saga Pattern Integration

---

# 15. Spring AOP

* AOP Concepts
* Join Point
* Advice
* Pointcut
* Aspect
* Proxy Types
* JDK Proxy
* CGLIB
* Self Invocation Problem

---

# 16. Spring Security

* Filter Chain
* Authentication
* Authorization
* JWT
* OAuth2
* OpenID Connect
* Method Security
* CSRF
* CORS
* Password Encoding
* Session Management
* SecurityContext
* Custom Authentication
* Resource Server

---

# 17. Caching

* Spring Cache
* Cache Manager
* Redis
* Caffeine
* Cache Eviction
* Cache TTL
* Cache Aside
* Write Through
* Cache Stampede
* Cache Penetration

---

# 18. Scheduling & Async

* @Async
* Executors
* TaskExecutor
* Scheduling
* Cron
* Fixed Delay
* Fixed Rate
* Virtual Thread Executors

---

# 19. Messaging

* Kafka
* RabbitMQ
* JMS
* Event Publishing
* Spring Events
* Retry
* Dead Letter Queue
* Idempotent Consumers
* Transactional Messaging

---

# 20. Reactive Programming

* Reactive Streams
* Reactor
* Mono
* Flux
* WebFlux
* Functional Endpoints
* Backpressure
* Reactive Transactions

---

# 21. Observability

* Spring Boot Actuator
* Health Indicators
* Metrics
* Micrometer
* OpenTelemetry
* Tracing
* Distributed Tracing
* Prometheus
* Grafana

---

# 22. Testing

* Unit Testing
* MockMvc
* WebMvcTest
* DataJpaTest
* SpringBootTest
* Testcontainers
* WireMock
* Mockito
* Integration Testing

---

# 23. Resilience

* Retry
* Circuit Breaker
* Timeout
* Bulkhead
* Rate Limiting
* Fallback
* Resilience4j

---

# 24. Configuration & Secrets

* Profiles
* Config Trees
* Vault
* Kubernetes Secrets
* Environment Variables
* Property Encryption

---

# 25. Deployment

* Docker
* OCI Images
* Layered JARs
* Kubernetes
* OpenShift
* Graceful Shutdown
* Readiness Probe
* Liveness Probe

---

# 26. Performance

* Startup Optimization
* Lazy Beans
* Native Image
* AOT
* Connection Pools
* Thread Pools
* HTTP Client Tuning
* Memory Optimization

---

# 27. Spring Boot Internals

* Auto Configuration Internals
* Bean Definition Registry
* Classpath Scanning
* Condition Evaluation
* Application Events
* Environment Processing
* Context Refresh
* Startup Sequence

---

# 28. Modern Spring Features (3.5 / 4.x)

* Virtual Thread Support
* AOT Improvements
* Native Image Enhancements
* Structured Logging
* OpenTelemetry Integration
* Improved SSL & Service Connections
* Enhanced Actuator Security
* Problem Details by Default
* Modern HTTP Client Support
* Migration from 3.x → 4.x ([Home][2])

---

# 29. Best Practices

* Constructor Injection
* Immutable DTOs
* Feature-based Package Structure
* Layered Architecture
* Hexagonal Architecture
* Modular Monolith (Spring Modulith)
* Clean Architecture
* Domain-Driven Design Integration

---

# 30. Interview Focus Areas (Staff/Principal)

* Bean Lifecycle Internals
* Auto Configuration Internals
* AOP Proxy Internals
* Transaction Internals
* Spring Security Filter Chain
* JPA Performance Tuning
* Threading Model
* Reactive vs MVC
* Native Images
* Production Debugging
* Memory Leaks
* Startup Failures
* Performance Bottlenecks
* Distributed Transactions
* Multi-tenancy
* Observability
* Zero-Downtime Deployment
* Backward Compatibility
* Framework Upgrade Strategy

[1]: https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-4.0-Release-Notes?utm_source=chatgpt.com "Spring Boot 4.0 Release Notes · spring-projects/spring-boot Wiki · GitHub"
[2]: https://spring.io/blog/2025/05/22/spring-boot-3-5-0-available-now/?utm_source=chatgpt.com "Spring Boot 3.5.0 available now"
