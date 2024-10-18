[< Back to the list of patterns](patterns_list.md)

# Saga Pattern

## Usage
This pattern helps maintain data integrity and consistency in distributed systems, making it a valuable tool for complex microservices architectures.

## Description
The Saga design pattern is used to manage distributed transactions in microservices architecture, 
ensuring data consistency across multiple services. One example of this is order processing in an e-commerce application.

Key aspects:
* **Sequence of Transactions:** A saga is a sequence of local transactions. Each transaction 
 updates the database and publishes an event to trigger the next transaction in the sequence.
* **Compensating Transactions:** If a transaction fails, the saga executes compensating transactions 
 to undo the changes made by the preceding transactions, ensuring data consistency.
* **Choreography vs. Orchestration:**
  * **Choreography:** Each service involved in the saga listens for events and decides when to act based 
 on those events. This approach is decentralized and allows services to operate independently.
  * **Orchestration:** A central coordinator (orchestrator) manages the saga, directing each service on 
what to do and when. This approach provides more control but can introduce a single point of failure.


[< Back to the list of patterns](patterns_list.md)
