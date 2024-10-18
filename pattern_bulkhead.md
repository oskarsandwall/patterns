# Bulkhead Pattern

## Usage
This pattern is particularly useful in microservices architectures, where services are distributed and interdependent.

## Description
By using this resilience strategy pattern the different parts of a system will be isolated.
This prevent failures from cascading and thus ensure that a failure in one service bring 
down an entire application.


Key aspects:
* **Isolation:** Similar to the compartments (bulkheads) in a ship’s hull, this pattern isolates
 different components or services into separate pools. If one component fails, the failure is
 contained within that pool, preventing it from affecting other parts of the system.
* **Resource Allocation:** Resources such as threads, memory, or connections are partitioned so
 that each pool has its own dedicated resources. This ensures that a failure in one component
 does not exhaust the resources needed by other components.
* **Fault Tolerance:** By isolating failures, the system can continue to function even if one
  part is experiencing issues. This increases the overall resilience and reliability of the system.
* **Cascading Failure Prevention:** The pattern helps prevent cascading failures, where a failure in
  one part of the system leads to failures in other parts.
