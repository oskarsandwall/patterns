[ UNDER CONSTRUCTION ]

# Publisher/Subscriber Pattern (Pub-Sub)

Tags: [Solution Architecture], [Event-Driven]

``` mermaid
flowchart TB
  classDef msg fill:#ddd,stroke:#333,stroke-width:0px;
  
  P1(Publisher 1)
  P2(Publisher 2)
  S1(Subscriber 1)
  S2(Subscriber 2)
  S3(Subscriber 3)
  M6["Message 6"]:::msg
  M5["Message 5"]:::msg
  M4["Message 4"]:::msg
  M3["Message 3"]:::msg
  M2["Message 2"]:::msg
  M11["Message 1"]:::msg
  M12["Message 1"]:::msg
  M13["Message 1"]:::msg
  
  subgraph P["Producers"]
    direction LR
    P1
    P2
  end
  
  subgraph B["Message Broker"]
    direction TB
    M4 ~~~ M3 ~~~ M2
  end
  
  subgraph C["Consumers"]
    direction LR
    S1
    S2
    S3
  end
  
  P1 --- M5 --> B
  P2 --- M6 --> B
  
  B --- M11 --> S1
  B --- M12 --> S2
  B --- M13 --> S3
```
