[< Back to the list of patterns](patterns_list.md)

# Command Query Responsibility Segregation (CQRS) Pattern

## Usage
Overall, CQRS is particularly useful in complex domains where read and write operations have different performance and scalability requirements.

## Description
This pattern is designed to separate the read and write operations of a data store into distinct models.

``` mermaid
flowchart LR
    CL[Client] --> U(UI)
  
    subgraph L [Logic]
        direction TB
        U-->CO(Command)
        U-->Q(Query)
    end

    subgraph S [Storage]
        CO-->WD[(Write Database)]
        Q-->RD[("Read Database<br>(Materialized View)")]
        WD-..->|Eventual Consistency|RD
    end
```
## Key features and benefits
1. **Separation of Concerns:** CQRS divides the application into two parts:
   - **Command Model**: Handles all the operations that change the state of the application (e.g., creating, updating, deleting data). Commands are task-based, meaning they represent actions like “book a hotel room” rather than simple data updates.
   - **Query Model:** Handles all the operations that retrieve data without modifying it. Queries return data transfer objects (DTOs) that are optimized for read operations.
2. **Optimized Models:** Each model is optimized for its specific purpose:
   - The **Command Model** can include complex business logic and validation rules to ensure data integrity.
   - The **Query Model** can be tailored for performance, allowing for efficient data retrieval and potentially using different data structures or databases.
3. **Asynchronous Processing:** Commands can be processed asynchronously, which helps in scaling the application and improving performance. This means that commands might be placed in a queue and processed later, rather than immediately.
4. **Eventual Consistency:** Since the command and query models are separate, the system may not always be immediately consistent. Instead, it achieves eventual consistency, where the query model is updated asynchronously to reflect the changes made by the command model.
5. **Scalability and Performance:** By separating read and write operations, CQRS allows each part to scale independently. This can lead to better performance and easier management of complex applications.
6. **Security and Permissions:** CQRS can simplify security management by isolating read and write operations, reducing the risk of exposing sensitive data inappropriately.

[< Back to the list of patterns](patterns_list.md)
