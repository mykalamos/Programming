# Microservices 2

# Architecture Summary

| Feature              | Description                                                                 | Advantages                                                                 | Disadvantages                                                                 |
|----------------------|-----------------------------------------------------------------------------|----------------------------------------------------------------------------|--------------------------------------------------------------------------------|
| **Modularity**        | System is broken into small, independent services                          | Easier to develop, test, deploy, and scale independently                    | Complexity in managing many services                                          |
| **Decentralized Data**| Each service manages its own database                                      | Improved scalability and autonomy                                          | Data consistency and integrity become harder                                  |
| **Technology Agnostic**| Services can use different languages and tech stacks                      | Flexibility in choosing the best tool for the job                          | Requires expertise in multiple tech stacks                                    |
| **Scalability**        | Services can be scaled independently based on load                        | Cost-effective resource utilization                                         | Requires complex infrastructure (e.g., container orchestration)              |
| **Fault Isolation**    | Failures in one service don't affect the entire system                    | Improves system resilience                                                  | Requires robust monitoring and fallback strategies                           |
| **Deployment Flexibility**| Services can be deployed independently                                  | Faster release cycles and continuous delivery                              | Deployment orchestration can be complex                                      |
| **Organizational Alignment**| Teams own and manage specific services (DevOps alignment)            | Enables team autonomy and parallel development                             | Coordination between teams can be challenging                                |
| **Inter-service Communication**| Services communicate over network (HTTP, messaging, etc.)         | Clear service boundaries                                                    | Network latency, retries, and error handling complexity                      |

# Managing Distributed Processes

| Technique                | Description                                                                 | Advantages                                                        | Disadvantages                                                        |
|--------------------------|-----------------------------------------------------------------------------|-------------------------------------------------------------------|----------------------------------------------------------------------|
| **Orchestration**         | A central service (orchestrator) controls and coordinates process flow     | Centralized control, easier to monitor and modify workflows       | Single point of failure, tight coupling to orchestrator              |
| **Choreography**          | Services react to events and coordinate themselves without central control | Loosely coupled, scalable, resilient to changes                   | Harder to track end-to-end flow, complex debugging                   |
| **Saga Pattern**          | A sequence of local transactions across services with compensation steps   | Maintains data consistency in distributed transactions             | Complex to implement and manage compensations                        |
| **Event-Driven Architecture** | Services communicate via asynchronous events (e.g., message queues)       | High decoupling, scalability, responsiveness                      | Eventual consistency, debugging and tracing are challenging          |
| **Distributed Tracing**   | Tracks and visualizes requests across services (e.g., OpenTelemetry, Jaeger) | Improves observability and debugging                              | Adds overhead, requires instrumentation in all services              |
| **Service Mesh**          | Infrastructure layer (e.g., Istio, Linkerd) for service-to-service communication | Built-in features for routing, retries, observability, and security | Operational complexity, learning curve                              |
| **Workflow Engines**      | Tools like Camunda or Temporal manage stateful workflows across services   | Handles complex long-running processes                            | Additional infrastructure and potential vendor lock-in               |
