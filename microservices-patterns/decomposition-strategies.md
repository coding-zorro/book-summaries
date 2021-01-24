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

This is a three step pr






