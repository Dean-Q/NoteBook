---
description: Some terms, read and write logic, simple cql queries
---

# How to use

## Basic Terms

* **Node**: The basic building block of cassandra, a node can be a physical server or a virtual server.
* **Datacenter**:  A group of related nodes that are configured together within a cluster for replication and workload segregation purposes. Not necessarily a separate location or physical data center. Datacenter names are case sensitive and cannot be changed.
* **Keyspace**: A namespace container that defines how data is replicated on nodes in each datacenter, the outermost container for data in Cassandra, it's familiar to traditional database, used to organize and manage tables, each keyspace has its own replica strategy and related tables.
* **Column Family**: A container for rows, similar to the table in a relational system. Called a table in CQL 3.
* **Partition Key**: A unique identifier for each row that is used to locate the location of the data in the cluster.
* **Replication Factor**: It’s the number of machines in the cluster that will receive copies of the same data.
* **Consistency Level**: A setting in which a read or write must enter several replicas before it is considered successful
* **Token**: Location identifier used to allocate data in Cassandra. Each node is responsible for a range of tokens, which ensures that the data is evenly distributed throughout the cluster

