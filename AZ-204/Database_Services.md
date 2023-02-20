### Key Value Store
- Just a key value store
- Schemaless
- Easily Scalable
- **Document Store** is NOSQL Database provide document storage, you can store JSON, XML here. This is subclass of key value store

### Graph Database
- In graph database, data structure that uses vertices (node, dots) and connect to other via edges.
- Use cases for graph db 
    - Fraud detection 
    - Real-time recommendation engines. 
    - Master data management (MDM) 
    - Network and IT operations. 
    - Identity and access management (IAM) 
    - Traceability in Manufacturing 
    - Contact Tracing 
    - Data Lineage for GDPR 
    - Customer 360-degree analysis (marketing) 
    - Product recommendations 
- **Apache Tinkerpoop** and **Gremlin**
    - Tinkerpoop is a graph computing framework for both graph databases (OLTP) and graph analytical systems (OLAP)
    - More of an adapter for commonly used graph databases such as Amazon Neptune, Neo4j, Cosmos Db. Since it is agnostic of the database it works with.
    - graph traversal language used here is Gremlin


### Azure Redis Cache
- Temporarly copying frequently accessed data into fast storage (memory) which is close to Application.
- Azure Redis Cache is accessible to Application withing Azure and outside to it.

### Azure Table
- NoSQL key/value database within Azure Storage Accounts
- Elements of the table
    - Partition Key 
        - Identifies the partition within the table
    - Row Key
        - Identifies the entity within a partition

### Azure Cosmos DB
- Types of datastorage offered by Cosmos
    - SQL (Document datastore)
    - Gremlin (graph datastore) 
    - MongoDB (document datastore)
    - Azure tables (key/value datastore)
- Cosmos DB's nature of communication is dependent upon the type of API you select - 
    - Core SQL API
    - Azure Table API
    - Mongo DB API
    - Cassandra API
    - Gremlin API
- Components of the Cosmos DB
    - Database 
        - This is the logical namespace for our data, users, permissions
    - Container 
        - A unit of compute
    - Collection
        - Billable entity
- Depth of the data in cosmosdb -  Cosmos Account -> Database -> Container -> Item 
- We scale the db in terms of request units unlike traditional databases. One Ru is 1kb item read from a Cosmos Db Container.
- Provisioned Throughput is ideal always on production. Throughput is evenly distributed to partitions. Autoscaling (Provisioned) - Can maximum RUs but minimum RUs would 10% of the Maximum. 
- Cosmos DB serverless - pay for what you use.
- Data consistency levels - 
![image](https://user-images.githubusercontent.com/36666451/172935682-c6009b3f-d5dc-46e9-ab70-6b690ab0695a.png)
 - Strong and Bounded staleness will use almost twice of the normal of RUs for a request 
- Items in container are divided into logical partition and physical partition have one or more logical partition and then there are replica set managed by physical partition for fault tolerance.    
- Hierarchy of the partitioning --> Physical Partition --> Replica Set --> Logical Partition --> Data        
- Partition key serves as the means of rounting the request to correct partition.
- Unique keys add layer of data integrity to their database.
- Basically Az takes the hash of the partition key valueand spreads the logical spaces across the physical partition, so it will calculate the hash value and map it to correct logical partition.
- Hot partition is the scenario when one of the physical partition is loaded with most the data in the database.
- Server Side Capabilities
    - Used withing database engine 
        - Stored Procedures
            - Supported by SQL API
            - Supports Javascript
            - Works on a single partition key
        - Triggers 
            - Supports Java Script
            - Pre or post
            - Not guaranteed to be executed, must be specified in the request
        - User defined Functions
            - Supports JS
            - Custom function that could be used in query
    - Outside of the database engine
        - Change feed
            - Just like an Azure Function where Cosmos DB trigger is used and every action on the collection is logged.
            - Can notify you for update or add action but not for delete, there is a workaround.
            - Not supported for Azure Table API
- Globally distributed and multi-model database, provides varieties of API to access the database.
- You priortize the regions as failover and make regions read, write only as well.
- It offers API for SQL, Mongo, Cassandra, Gremlin. With Cosmos DB we can run mutliple database engines
- Database as a service - serverless
- Cost is determined with the help of Request Units
- Partitioning and Indexing
- Phycial Partiotions that comprise compute hardware resources and it contains logical partitions
- Container is basic abstraction of data sets, where it would span through multiple partitions and this contains your data.
- Every document is identifide by it's partition key and row key.
- Security 
- Supports HTTPS and TLS
- Master keys for admins and resource tokens for clients
- Key-value
- Graph
- Column-family
- Indexing is done automatically.
- Data Replication between Azure Regions is automatic.
- Containers
    - They are useful for scalability, Idea here is to separate different Azure Cosmos Db into container so that each one is user configurable and can be a different API based.
- Cosmos DB has two capacity modes
    - Provisioned throughput 
        - Sets certain RUs to the container, better when traffic is already predicted
    - Serverless
        - No prior provisioning of the capacity here
        - Could be used when workload is unpredictable
- Throughput strategies when creating databse and container
    - Dedicated
        - Throughput exclusive to a container
    - Shared 
        - Throughout is shared among the container
- Two ways to read data from Cosmos DB
    - Points Reads - Key/value lookup on a Single Item ID and partition key - 1 RUs 
    - Queries - A query allows you to return multiple items - At least 2.3 RUs 
- Request Units 
- Azure Cosmos DB exposes a "change feed". The change feed support in Azure Cosmos DB works by listening to a database container for changes. DynamoDB has streams. Change feed is supported by all APIs except Table API. 
![image](https://user-images.githubusercontent.com/36666451/196996297-9bec247c-2adf-4b3a-8082-bb5501632150.png)

- Partitioning in Cosmos DB 
    - Each item in a container has a partition key. Partition key is used for scaling purposes. Each Cosmos DB instance has Physical Partition and Logical Partition. Physical partition are the reserved physical space and compute on SSD whereas Logical Partition is a logical partition within physical partition and logical partition from values of Partition Key.