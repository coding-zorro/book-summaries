# Microservices Patterns

Microservice architecture (microservices) is an architectural style that functionally decomposes an application into a set of services, where each service has a focused and cohesive set of responsibilities.

Advantages of Monolith architecture-
- Simple to develop
- Easy to test
- Easy to develop
- Easy to make radical changes 
- Easy to scale

Downsides of Monolith architectures-
- Becomes complex over tim
- Slower development and corrections
- Commit to deployment is long and arduous
- Scaling(at component levels) is difficult
- Reliability and fault isolation is poor
- High chance to getting stuck with older technologies

Three ways to scale an application-
- Replication: create many instances of the application
- data partitioning
- Functional decomposition: by breaking down into small functional units

Differences with SOA -
- SOA has global data models
- SOA has shared databases
- SOA uses heavyweight protocols such as SOAP and Enterprise Bus
- SOA are typically part of monolithic applications

Advantages of Microservices -
- Enables continuous delivery
- Better testability through automated tests
- Small and easily maintainable
- Deployed independently
- Scaled independently
- Teams can be autonomous and loosely coupled
- Better fault isolation
- Enables experimentation and adoption of new technologies

Drawbacks of Microservices -
- Finding the right set of services is challenging
- Complexity of distributed systems
- Deploying features across multiple services is complex

Distributed monolith -
- created due to incorrect functional decomposition
- services are coupled
- services have to be deployed together

## Pattern Language

A pattern language is a good way to describe system architecture and design. Its objective and enables better decision making. A pattern structure uses three sections -
- Forces - The issues that are addressed when solving a problem
- Resulting context - The consequences of applying a pattern. There can be three kinds of consequences -
    - Benefits - Forces that have been resolved
    - Drawbacks - Unresolved forces
    - Issues - New problems 
- Related patterns - Relationship between this pattern and other patterns. There can be five kinds -
    - Predecessor - The pattern that motivates the need for this pattern
    - Successor - A pattern that solves an issue introduced by this pattern
    - Alternative - A pattern that provides an alternate solution
    - Generalization - A general solution to a problem
    - Specialization - A specialized form of a particular pattern

## Microservice architecture pattern language

The Microservice architecture pattern language is a collection of patterns that help you architect an application using the microservice architecture. The patterns are divided into three layers:
- Infrastructure patterns - solves infrastructure issues
- Application infrastructure - solves issues that affect both infrastructure and applications
- Application patterns - solves development issues

There are two decomposition patterns: 
- Decompose by business capability - organizes services around business capabilities
- Decompose by subdomain -  organizes services around domain driven design (DDD) subdomains.

Interprocess communication (IPC) is an important part of the microservice architecture. They are organized into five groups:
- Communication style
- Discovery
- Reliability
- Transactional messaging
- External API

Service deployment patterns 
- Multiple services per host - Traditional approach of deploying services using their language-specific packaging, such as WAR files
- Serverless deployment - modern approach, which runs your code without you having to worry about managing the infrastructure
- Single service per host - A modern approach using containers, which encapsulates a service’s technology stack
- Service deployment platform - Automated, self-service platform for deploying and managing services

Patterns to design observable services:
- Health check API
- Log aggregation
- Distributed tracing
- Exception tracking
- Application metrics
- Audit logging

Four useful metrics for assessing software development are as follows:
- Deployment frequency - How often software is deployed into production
- Lead time - ime from a developer checking in a change to that change being deployed
- Change failure rate - Percentage of changes that result in a production problem







