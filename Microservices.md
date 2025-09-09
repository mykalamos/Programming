# Microservices

## Architectural style
- an application as a collection of services
    - small
    - independently deployable
    - each with single business capability

### 🔑 Key Characteristics of Microservices

| Characteristic           | Description                                                                 |
|--------------------------|-----------------------------------------------------------------------------|
| **Single Responsibility**| Each service handles one specific business capability                       |
| **Independent Deployment**| Services can be updated and deployed separately                            |
| **Technology Agnostic**  | Each service can use different languages, frameworks, and databases         |
| **Resilience**           | Failures in one service should not cascade to others                        |
| **Scalability**          | Services can scale independently based on demand                            |
| **Autonomy**             | Services own their logic and make decisions independently                   |
| **Decentralized Governance** | Teams have freedom to choose tools and practices                     |
| **Data Ownership**       | Each service owns its own database; no shared databases or direct access    |

TODO saga vs 2pc