

[< Back to the list of patterns](patterns_list.md)

# Kafka - Basic Solution Architecture
Tags: **[Solution Architecture], [Event-Driven], [Distributed], [Kafka]**

## Usage

## Description
...

``` mermaid
graph TD
    subgraph Kafka Cluster
    Broker1[Broker 1] -->|Replicates data to| Broker2[Broker 2]
    Broker2 -->|Replicates data to| Broker3[Broker 3]
    Broker1 -.->|Syncs with| ZK[Zookeeper]
    Broker2 -.->|Syncs with| ZK
    Broker3 -.->|Syncs with| ZK
    end

    subgraph Producers
    P1[Producer 1] -->|Sends data to| Broker1
    P2[Producer 2] -->|Sends data to| Broker2
    P3[Producer 3] -->|Sends data to| Broker3
    end

    subgraph Consumers
    C1[Consumer 1] -->|Reads data from| Broker1
    C2[Consumer 2] -->|Reads data from| Broker2
    C3[Consumer 3] -->|Reads data from| Broker3
    end
```


[< Back to the list of patterns](patterns_list.md)
