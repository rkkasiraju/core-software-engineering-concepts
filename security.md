# 1. Security Fundamentals

* CIA Triad
* Authentication
* Authorization
* Accounting (AAA)
* Non-Repudiation
* Defense in Depth
* Least Privilege
* Zero Trust
* Threat Modeling
* Security by Design

---

# 2. Identity & Access Management (IAM)

* Users
* Groups
* Roles
* Permissions
* RBAC
* ABAC
* PBAC
* Service Accounts
* Identity Federation
* Single Sign-On (SSO)
* Multi-Factor Authentication (MFA)

---

# 3. Authentication

* Username/Password
* API Keys
* Basic Authentication
* Digest Authentication
* Session-Based Authentication
* Token-Based Authentication
* Certificate-Based Authentication
* Mutual TLS (mTLS)
* Passwordless Authentication
* Biometric Authentication (Awareness)

---

# 4. Authorization

* RBAC
* ABAC
* Resource-Based Authorization
* Policy-Based Authorization
* Fine-Grained Authorization
* Method-Level Security
* URL-Level Security
* Data-Level Security

---

# 5. OAuth2 & OpenID Connect

* OAuth2 Roles
* Authorization Code Flow
* PKCE
* Client Credentials Flow
* Device Flow
* Refresh Tokens
* Access Tokens
* Scopes
* Claims
* OpenID Connect
* ID Tokens
* UserInfo Endpoint

---

# 6. JWT & Token Security

* JWT Structure
* JWS
* JWE
* Token Signing
* Token Encryption
* Claims
* Expiration
* Refresh Tokens
* Token Revocation
* Token Rotation

---

# 7. Session Management

* HTTP Sessions
* Session Cookies
* Secure Cookies
* HttpOnly
* SameSite
* Session Fixation
* Session Hijacking
* Stateless Sessions

---

# 8. Cryptography

* Symmetric Encryption
* Asymmetric Encryption
* Hashing
* Digital Signatures
* HMAC
* Key Exchange
* Random Number Generation
* Key Rotation

---

# 9. PKI & Certificates

* X.509 Certificates
* Certificate Authority (CA)
* Certificate Chain
* TLS Certificates
* CSR
* Certificate Rotation
* Revocation
* Trust Stores
* Key Stores

---

# 10. TLS & HTTPS

* SSL vs TLS
* TLS Handshake
* TLS Versions
* Cipher Suites
* Perfect Forward Secrecy
* HTTPS
* Mutual TLS
* TLS Termination

---

# 11. Secrets Management

* Password Storage
* API Keys
* Secrets Managers
* Vault
* Kubernetes Secrets
* Cloud Secret Stores
* Secret Rotation
* Dynamic Secrets

---

# 12. API Security

* API Authentication
* API Authorization
* Rate Limiting
* Throttling
* API Gateway Security
* Input Validation
* Output Validation
* Request Signing
* Replay Attack Prevention

---

# 13. Application Security

* Input Validation
* Output Encoding
* Secure Coding
* Secure Defaults
* Error Handling
* Exception Sanitization
* Security Headers
* Dependency Security

---

# 14. OWASP Top 10

* Broken Access Control
* Cryptographic Failures
* Injection
* Insecure Design
* Security Misconfiguration
* Vulnerable Components
* Authentication Failures
* Software Integrity Failures
* Logging & Monitoring Failures
* SSRF

---

# 15. Common Attack Vectors

* SQL Injection
* NoSQL Injection
* Command Injection
* XSS
* CSRF
* SSRF
* XXE
* Clickjacking
* Path Traversal
* File Upload Attacks
* Open Redirect
* Deserialization Attacks

---

# 16. Secure Communication

* HTTPS
* TLS
* mTLS
* Service-to-Service Authentication
* Certificate Rotation
* Secure Messaging
* Kafka Security
* gRPC Security

---

# 17. Cloud Security

* Shared Responsibility Model
* IAM
* Network Security
* Security Groups
* WAF
* DDoS Protection
* Encryption
* Cloud Audit Logs
* Cloud Compliance

---

# 18. Kubernetes Security

* Pod Security
* Network Policies
* RBAC
* Admission Controllers
* Image Security
* Secret Management
* Runtime Security
* Service Mesh Security

---

# 19. Container Security

* Image Scanning
* Minimal Images
* Non-Root Containers
* Runtime Security
* Image Signing
* Supply Chain Security

---

# 20. Database Security

* Authentication
* Authorization
* Encryption at Rest
* Encryption in Transit
* Field-Level Encryption
* Row-Level Security
* Data Masking
* Audit Logging

---

# 21. Logging & Auditing

* Audit Logs
* Security Events
* Access Logs
* Immutable Logs
* SIEM Integration
* Alerting
* Incident Response

---

# 22. DevSecOps

* SAST
* DAST
* IAST
* SCA (Software Composition Analysis)
* Secret Scanning
* Image Scanning
* Policy as Code
* Security Gates
* SBOM

---

# 23. Compliance & Governance

* GDPR
* PCI DSS
* HIPAA (Awareness)
* SOC 2
* ISO 27001
* Data Classification
* Data Retention
* Privacy by Design

---

# 24. Security Architecture

* Defense in Depth
* Zero Trust Architecture
* Secure Network Design
* Secure API Design
* Identity Architecture
* Threat Modeling
* Risk Assessment

---

# 25. Incident Response

* Detection
* Containment
* Eradication
* Recovery
* Postmortem
* Forensics
* Root Cause Analysis

---

# 26. Security Testing

* Unit Security Tests
* Integration Security Tests
* Penetration Testing
* Vulnerability Assessment
* Fuzz Testing
* Red Team / Blue Team (Awareness)

---

# 27. Security in Microservices

* API Gateway Security
* Service-to-Service Authentication
* mTLS
* JWT Propagation
* Distributed Authorization
* Secret Distribution
* Multi-Tenant Security

---

# 28. AI & Modern Security

* LLM Security
* Prompt Injection
* RAG Security
* Model Access Control
* AI Data Leakage
* AI Supply Chain Security

---

# 29. Common Production Problems

* Expired Certificates
* Secret Leakage
* Token Expiration Issues
* JWT Misconfiguration
* OAuth Misconfiguration
* CORS Misconfiguration
* Missing Authorization Checks
* Privilege Escalation
* Insecure API Exposure
* Dependency Vulnerabilities
* Container Escape Risks
* Kubernetes RBAC Misconfiguration
* Weak Password Policies
* Sensitive Data Logging

---

# 30. Interview Focus Areas (Staff/Principal)

* Authentication vs Authorization
* OAuth2 vs OpenID Connect
* JWT vs Session-Based Authentication
* mTLS Architecture
* API Security Design
* Zero Trust Implementation
* Secret Management Strategy
* Certificate Lifecycle Management
* Secure Microservices Communication
* OWASP Mitigation Strategies
* Secure Kubernetes Deployments
* DevSecOps Pipeline Design
* Identity Federation
* Threat Modeling
* Incident Response Strategy
* Compliance Considerations
* Security Trade-offs
* Security Architecture Reviews
* Production Security Troubleshooting
* Secure System Design

---

## Recommended Study Order

Security is easiest to master if you build it in layers:

1. **Security Fundamentals**
2. **Authentication & Authorization**
3. **OAuth2, OpenID Connect & JWT**
4. **Cryptography & TLS**
5. **API & Application Security**
6. **OWASP Top 10 & Attack Vectors**
7. **Spring Security**
8. **Microservices & Service-to-Service Security**
9. **Cloud, Kubernetes & Container Security**
10. **DevSecOps & Supply Chain Security**
11. **Security Architecture & Incident Response**

---
