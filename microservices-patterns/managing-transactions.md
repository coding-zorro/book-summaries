# Managing Transactions

In a microservice architecture, transactions that are within a single service can still use ACID transactions. The challenge, however, lies in implementing transactions for operations that update data owned by multiple services.
<br><br>
**Saga** is a pattern to maintain data consistency across services using a sequence of local transactions that are coordinated using asynchronous messaging. They lack the isolation property of ACID transactions. When there are failures, the local transactions are be rolled back using compensating transactions.
<br><br>
Two different coordination logic in sagas -
- **Choreography** - The participating services communicate using events which trigger local transactions within the services.
- **Orchestration** - A Saga orchestrator(a separate class) sends command messages to participating services telling them which operations to perform.

<br><br>
Lack of Isolation can cause the following anamolies which needs to be overcome -
- Lost updates - One saga overwrites without reading changes made by another saga.
- Dirty reads - A transaction or a saga reads the updates made by a saga that has not yet completed those updates.
- Non repeatable reads - Two different steps of a saga read the same data and get different results because another saga has made updates.

<br><br>
Countermeasures to overcome lack of Isolation -
- *Semantic* - lock—An application-level lock.
- *Commutative updates* - Design update operations to be executable in any order.
- *Pessimistic view* - Reorder the steps of a saga to minimize business risk.
- *Reread value* - Prevent dirty writes by rereading data to verify that it’s unchanged before overwriting it.
- *Version file* — Record the updates to a record so that they can be reordered.
- *By value* — Use each request’s business risk to dynamically select the concurrency mechanism.
