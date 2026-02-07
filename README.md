# Kafka

- Contains code, concepts, and topics related to Apache Kafka.

- [Kafka](#kafka)
  - [Why Kafka?](#why-kafka)
    - [The Problem](#the-problem)
    - [The Solution](#the-solution)
  - [Why Use Kafka?](#why-use-kafka)
    - [Use Cases of Kafka](#use-cases-of-kafka)


---

## Why Kafka?

### The Problem

- If you've data interaction between source systems and target systems, and when they increase in numbers, the integration becomes extremely difficult. Ex: Assume that there are 4 source systems, and 6 target systems, in such a case, you might need to write `6 * 4 = 24` integrations.
- Each integration may come with difficulties around:
  1. Protocol &mdash; how the data is transported (TCP, HTTP, REST, FTP, JDBC, etc).
  2. Data Format &mdash; how the data is parsed (Binary, CSV, JSON, Avro, Protobuf, etc).
  3. Data Schema & Evolution &mdash; how the data is shaped and change during the course of newer requirements.
- Each source system will have an **increase load** from the connections.

### The Solution

> We decouple the data streams and systems.

```terminal
  source-1      source-2      source-3      source-4
      |             |             |             |
      |             |             |             |
      +-------------+-------------+-------------+
                        |
                        |
                      KAFKA
                        |
                        |
      +--------+--------+--------+--------+--------+--------+
      |        |        |        |        |        |        |
  target-1  target-2  target-3  target-4 target-5 target-6  target-7
```

- We still have the same source systems and target systems present, but now the integrations are decoupled by making use of **KAFKA**.
- Apache Kafka will have the streaming data that has been ***produced* by source systems**, and which will be ***consumed* by target systems**.
- Example:
  - Source Systems: Website Events, Pricing Data, Financial Transactions, and User Interactions.
  - Target Systems: Database, Analytics, Email System, and Audit.

---

## Why Use Kafka?

- Created by LinkedIn, now an open source project, which is mainly maintained by Confluent, IBM, and Cloudera.
- It's Distributed, Resilient Architecture, Fault Tolerant.
- Provides Horizontal Scalability:
  - Can scale to 100s of brokers.
  - Can scale to millions of messages per second.
- High Performance &mdash; Realtime latency is < 10ms.
- Used by 2000+ firms, 80% of Fortune 100 companies:
  - LinkedIn, AirBnb, Netflix, Uber, Walmart, etc., are some big companies that make use of Apache Kafka.

### Use Cases of Kafka

Apache Kafka can be used for the following use cases:

- Messaging System.
- Activity Tracking.
- Gather metrics from many different locations.
- Application logs gathering (one of the first use cases for Kafka).
- Stream Processing (with Kafka Streams API).
- De-coupling of system dependencies.
- Integration w/ Spark, Flink, Storm, Hadoop, and many other Big Data Technologies.
- Micro-services pub/sub interaction.

***Real World Examples***

- Netflix uses Kafka to apply recommnedations in real-time while you're watching TV shows.
- Uber uses Kafka to gather user, taxi, and trip data in real-time to compute and forecast demand, and compute surge pricing in real-time.
- LinkedIn uses Kafka to prevent spam, collect user interactions to make better connection recommendations in real-time.

> Summary:  Kafka is a transportation mechanism which allows huge data flow across different systems.
