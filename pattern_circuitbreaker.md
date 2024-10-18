[< Back to the list of patterns](patterns_list.md)

# Circuit Breaker Pattern

## Usage
This pattern is particularly useful in distributed systems like microservice architectures to prevent 
cascading failures and improve overall system stability and resilience.

## Description
This resilience strategy pattern is used to prevent a system from repeatedly trying to execute an operation that’s likely to fail.

Key aspects:
* **Failure Detection:** The circuit breaker monitors the number of recent failures. If the failures exceed a certain threshold,
  the circuit breaker trips and stops further attempts to execute the operation.
* **State Management:** The circuit breaker can be in one of three states:
  * **Closed:** Normal operation, where requests are allowed through.
  * **Open:** Requests are blocked for a specified period to allow the system to recover.
  * **Half-Open:** A limited number of requests are allowed through to test if the issue has been resolved.
* **Fallback Mechanism:** When the circuit breaker is open, the system can provide a fallback response or
  an alternative action to handle the failure gracefully.
* **Recovery:** After a specified timeout, the circuit breaker transitions to the half-open state to test if
  the underlying issue has been resolved. If successful, it returns to the closed state; otherwise, it reopens.

[< Back to the list of patterns](patterns_list.md)
