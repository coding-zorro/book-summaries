# Interprocess Communication

The recommended architecture is to use loosely coupled services that communicate using asychronous messaging. Synchronous protocols such as REST should be used for communicating with external applications.
<br><br>
Multiple dimensions of interprocess communication -
- *One to one*: Each client request is processed by only one service
- *One to many*: Each request is processed by many services
- *Synchronous*: The client blocks while its waiting for a response from a service
- *Asynchronous*: The client doesn't block and the service does not respond immediately
- *One way notifications*: client sends a request to service and does not expect a response
<br><br>
Two types of one to many interactions-
- *Publish/Subscribe*: A message from a client is consumed by zero or more services
- *Publish/Async response*: The client waits for a certain amount of time for response after sending a message 
<br><br>
API-first design is essential.
<br><br>
**Versioning Services**<br>
- Major - when an incompatible change is made to the API
- Minor - when a backward compatible enhancement is made to the API
- Patch - when a backward compatible defect is made to the API
<br><br>
**Robustness principle**<br>
Services should provide default values for missing request attributes. Similarly, clients should ignore any extra response attributes.
<br><br>
Two kinds of message formats -
- Text such as XML or JSON
- Binary such as Avro. This forces an API first approach

## Synchronous Communication
**Remote procedure invocation**<br>
The business logic in the client invokes a proxy interface , implemented by an RPI proxy adapter class. The RPI proxy makes a request to the service. The request is handled by an RPI server adapter class, which invokes the service’s business logic via an interface. It then sends back a reply to the RPI proxy, which returns the result to the client’s business logic. The proxy interface usually encapsulates the underlying communication protocol.
<br><br>
### REST
A *Resource* represents a single business object. HTTP verbs and URLs are used to command or query the resources. Its documented using a Open API specification. REST maturity model -
- Level 0 - Clients make POST requests to a single URL on the service and the details of the action and target are included in the request
- Level 1 - Services supports the concept of Resources. The POST method is used for all requests.
- Level 2 - Services supports appropriate HTTP methods.
- Level 3 - Based on HATEOS principle. The representation of a resource contains links for actions(that can be performed on the resource) and its children(or parents).
<br><br>
Challenges in REST -
- Fetching multiple resources in a single request. This can be overcome by a resource representation containing details of related resources when requested using query params
- Mapping operations to HTTP methods. We may have to use URLs or Query params to support actions which are not possible through HTTP methods.
- Both service and client must be available.
- Clients must be knowing the locations of the services
<br><br>
Fault Tolerance in REST -
- Network timeouts. Use timeouts when waiting for a response
- Rate limiting. Impose a limit on the number of outstanding requests that a client can make to a particular service.
- Circuit breaker pattern. 
<br><br>
Service Discovery. Key components are - <br>
- Service registry - a database of network locations of services
- Service discovery - When a client invokes a service, the service registry is used to locate the service.
- Two ways of implementing service discovery
    - Application level. The services and clients directly interact with the service registry
    - Platform level. Built-in service registry and discovery provided by platforms such as kubernetes.
<br><br>
## Asynchronous messaging
A message broker is used as an intermediary between the services. Asynchronous messages through brokerless architecture is also possible where the clients send a message to the service and do not expect a response.
<br><br>
Messages. There are three types -
- Document
- Command
- Event
<br><br>
Channels. Two kinds - 
- Point to point. Clients sends a message to the service with the message id and a reply channel to which the service responds.
- Publish/Subscribe. 

### Message Broker
Message broker is an infrastructure component through which services communicate using messages. The sender writes the message to the message broker, and the message broker delivers it to the receiver. A message broker buffers messages until the consumer is able to process them. <br>
Factors for consider when selecting a message broker -
- Supported programming languages
- Supported messaged standards
- Message ordering
- Delivery guarantees
- Persistence
- Durability
- Scalability
- Latency
- Competing consumers
<br><br>
**Advantages of Message brokers**<br>
- Loose coupling
- Message buffering
- Flexible communicatio
- Explicit interprocess communication
<br><br>
**Downsides**<br>
- Potential performance bottleneck
- Potential single point of failure
- Additional operational complexity
<br><br>
**Competing receivers and message ordering**<br>
Modern message brokers use partitioning(shards) where the related messages are targeted to the same shard so that the same receiver processes them.
<br><br>
**Handling duplicate messages**<br>
Two ways to handle it -
- Writing idempotent receivers.
- Track messages using an id and discard the duplicates
<br><br>
**Transactional Messaging**<br>
An OUTBOX table is also updated by the service during transactions. A *Message relay* component reads the OUTBOX tables and publishes them as messages to a message broker. One other approach is the *Message relay* can tail the OUTBOX DB commit logs and publish them as messages to a message broker.
<br><br>

### Improving synchronous communication
**Data replication**<br>
Data replication can be used to minimize synchronous requests and improve data availability. A service has to maintain a replica of data that it needs from other services. The replica is kept up-to date by subscribing to events from those other services.
<br><br>
**Respond before processing**<br>
- Validate the request using only the data available locally.
- Update its database, including inserting messages into the OUTBOX table.
- Return a response to its client. The client will have to query later or repeatedly poll to get the latest status on the request.




