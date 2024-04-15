# Types of Storage Type
**main thing to consider when selecting storage solution is to consider the time needed to retrieve the data**


## Cache
- in-memo data, low latency, limited in size by the amount of memo available, content will lost if the machine hosting the cahceh shuts down
### Memory Store
- Redis/Memcached  : High availability / failover replicas
- Memorystore caches can be used with

## Persistent Storage
- durable block storage
- can be attached to VMs in GcE and GKE
- File sys can be created
- Not directly attached to physical servers hosting the VMS but are network accessible
- VMs can have locally  attached SSD, but the data on the drives is lost whent he cm is terminated
- SSD: low latency, consisten performance for both random access and sequential access patterns
- HDDS: longer latencies but cost less, large amount of data, perform batch operation
- Can be mounted on multiple VMs to provide multireader storage
## Object Storage
- Cannot operate on part of the file
- Does not support concurrency and locking, if multiple clients are writing to a file, then the alst data written to the file is stored and persisted
- Suitable for large volume of data without requiring any consistent data structure
- no filesys provided
### standard, nearline, coleline and archive
### Regional, dual regional and multi-regional storage
### Versioning and Object Life cycle Management
- The latest version is called live version
- Life cycle management : conditoin + action


## Storage Types When Planning a Storage Solution


# Storage Data Model
## Object: Cloud storage
- Cannot use object storage commnads to read blocks of data or overwrite parts of the object
- Copy it to server, make the changek copy the updated version back to theobject storage system
- Suitable for large volumes of data and do not need fine-grained access to the data
- Archieved data, ML tarining data, Old IoT

## Relational: Cloud Sql and Cloud Spanner
- Users have consistent view of data
- Cloud SAL or Cloud spanner support transactions (a set pf operations that is guaranteed ot succeed or faio in its entirety, roll back the partially executed transactions)
- Cloud sql: Scale vertically, by running on servers with more memory and more CPU: web application, e commerce applications
- Cloud Spanner: extremly large volumne of data and globally distributed wiith consistency and transaction integrity across al server: global supply chain, financial services aplications
## Analytical: BigQuery
- for data warehouse and analytical applications, provide storag plus query, statistical, machine learniiing analysis tools

## NoSQL: Cloud Firestroe and BigTable

-  no fixed structure or schema ( schema defines that kinds of sttributes cna be stored)
- Developers can store different attributes in diff records

### Firestore
- data is organized into a structure clalled a document, key- value pair - entities
- suitable fore non analytical and non relational storage needs, good for product catalogs
- support transactions and indexes
- Datastore, namespace: scheme to group tables: kind- tables
- Native Mode: documents and collections

### BigTable
- Wide colume database
- run in cluster and scale up horizontally
- suitable for high data volume and high velocity ingest of data: Time series, IoT, Financial Applications
(writing data at consistently high rates and in large volume)


# Choosing a Storage Solution： Guidelines

Read and Write Patterns; Consistency; Transaction Support; Cost; Latency

***Vertical and Horizontal Scaling DataBase***

Scaling a database can be done in two primary ways: horizontally and vertically. Let's break down each approach with an explanation and example:

**Vertical Scaling (Scaling Up):**

Vertical scaling involves increasing the capacity of a single server by adding more resources such as CPU, RAM, or storage.

This approach is typically easier to implement initially, as it involves upgrading existing hardware.
However, there's a limit to how much a single server can be scaled vertically, and it can become costly beyond a certain point.

Examples of vertical scaling include upgrading a server's CPU from dual-core to quad-core, or adding more RAM or storage to a server.

**Horizontal Scaling (Scaling Out):**

Horizontal scaling involves adding more servers to distribute the load across multiple machines.
This approach is more scalable in the long term and can handle increased traffic by adding more servers to the cluster.

Horizontal scaling often requires more sophisticated architecture and software solutions to distribute and manage data across multiple nodes.
It can also provide better fault tolerance because if one server fails, others can continue to serve requests.

Examples of horizontal scaling include sharding a database across multiple servers based on some criteria (e.g., customer ID, geographical region) or setting up a cluster of web servers behind a load balancer.***