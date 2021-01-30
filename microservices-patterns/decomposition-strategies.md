# Decomposition Strategies

The architecture of a software application is its high-level structure, which consists of constituent parts and the dependencies and relationships between those parts. 

### 4+1 view model of software architecture
This model defines four different views of the software architecture -
- Logical view - software elements that are created by developers.
- Implementation view - output of the build system
- Process view - the components at runtime
- Deployment view - processes running on machines

The +1 in this model refers to scenarios. Each scenario describes how the various architectural components within a particular view collaborate in order to handle a request.

## Different Architecture styles 
### Layered Architecture<br>
Software elements are organized into layers -
- Presentation layer
- Business logic layer
- Persistence layer

### Hexagonal Architecture
- Applications have one or more inbound adapters that handle requests from outside.
- Applications has one or more outbound adapters(example - DAO) that are invoked by the business logic
- Applications don't depend on adapters. The dependency is through portss(Interfaces in Java).

### Service
- A service is a standalone, independently deployable software component that imple- ments some useful functionality. 
- A service has an API that provides its clients access to its functionality. The API encapsulates its implementation details.
- Each service has its own architecture and, potentially, technology stack. 
- Services are loosely coupled
- Shared libraries - Use libraries for functionalities that changes less often and use it in the services
- Size of a service - Size doesn't really matter. The service should be able to developed by a small team with minimal lead time and minimal collaboration


## Defining a microservice

This is a three step process which is likely to iterative and creative -
1. Identify system operations
2. Identify the services
3. Define service APIs and collaborations

A **system operation** is an abstraction of a request that the application must handle. It’s either a command, which updates data, or a query, which retrieves data. <br>

Services are based on business concepts and not, technical concepts. Two main strategies for decomposing services -
1. define services corresponding to business strategies
2. organize services around domain driven design sub-domains

Obstacles to decomposition -
- Network latency
- Synchronous communication
- Data consistency across services
- God classes

The domain model is derived primarily from the nouns of the user stories, and the system operations are derived mostly from the verbs. <br>
An organization’s business capabilities are identified by analyzing the organization’s purpose, structure, and business processes. Each business capability can be thought of as a service, except it’s business-oriented rather than technical.<br>
DDD has two main concepts used in the microservice architecture -
- sub-domains - part of the domain. A domain is DDD's application's problem space.
- bounded contexts - a service or a set of services

Decomposition guidelines -
- Single responsibilty principle
- Common closure principle









