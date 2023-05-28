
[< Back to the list of patterns](patterns_list.md)

# Event Streaming Pattern
Tags: **[Solution Architecture], [Event-Driven], [Distributed]**

## Usage

## Description
This pattern has similarities with the [Publish/Subscribe pattern](pattern_pubsub.md), but where pub-sub typically deletes the messages when all subscribers have received the messages in an _event stream_ are not deleted. The stream can be seen as the _immutable_ history of "the world" stored as an _ordered sequence_ of events. If information needs to be removed this is controlled by the use of retention policies. 

``` mermaid
flowchart TB
  classDef msg fill:#ddd,stroke:#333,stroke-width:0px;
  
  ES1["Event Source 1"]
  ES2["Event Source 1"]
  ES3["..."]
  
  E5["..."]
    
  subgraph ESS["Event Sources"]
    direction LR
    ES1 ~~~ ES2 ~~~ ES3
  end

  subgraph ES["Event Streams"]
    direction LR
    E5 ~~~ E4 ~~~ E3 ~~~ E2 ~~~ E1
  end
  
  subgraph C["Consumers"]
    direction LR
    C1 ~~~ C2 ~~~ C3
  end
  
  ESS --> ES ---> C
```

As with the [Publish/Subscribe pattern](pattern_pubsub.md) streams/topics are used by consumers (also called _event sinks_ and _event processors_) to specify which events they wish to be notified about. Some platforms (like Kafka) allow you to partition stream events even further to enable parallel processing, allowing for better scalability.

``` mermaid
flowchart TB
  classDef msg fill:#ddd,stroke:#333,stroke-width:0px;
  classDef part1 fill:#3333ff,stroke:#000,stroke-width:1px;
  classDef part2 fill:#33FFFF,stroke:#000,stroke-width:1px;
  
  E1[" "]:::part1
  E2[" "]:::part2
  E3[" "]:::part2
  E4[" "]:::part1
  E5[" "]:::part2
  E6[" "]:::part1
  
  E71[" "]:::part1
  E72[" "]:::part1
  E73[" "]:::part1
  
  E81[" "]:::part2
  E82[" "]:::part2
  E83[" "]:::part2
  
  EP1["Event Processor 1"]
  EP2["Event Processor 2"]
    
  subgraph ESS["Events"]
    direction LR
    E6 ~~~ E5 ~~~ E4 ~~~ E3 ~~~ E2 ~~~ E1
  end

  subgraph ES["Event Stream"]
    direction LR
    subgraph P1["Partition 1"]
      direction LR
      E71 ~~~ E72 ~~~ E73
    end

    subgraph P2["Partition 2"]
      direction LR
      E81 ~~~ E82 ~~~ E83
    end
  end
  
  ESS --> P1 & P2
  P1 --> EP1
  P2 --> EP2
  
```

[< Back to the list of patterns](patterns_list.md)
