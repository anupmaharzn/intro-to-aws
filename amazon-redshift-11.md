# Amazon RedShift

- Amazon Redshift is a cloud-based service or a data warehouse service that is used for collecting and storing data.

- Also, its enables a user to analyze the data using BI tools and simplifies the process of handling large scale data sets.

- `adv`

    - high performance
    - low cost
    - scalability
    - availability
    - security
    - flexibility

## Architecture


![amazon-redshift](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/298fc954-afdd-4b11-b3a6-c3d6264e3b6d)


![aws-arch](https://github.com/anupmaharzn/intro-to-aws/assets/34486226/a7fe3aac-dc49-4caf-863e-9836159ff5ad)



- **Client applications**
    -  Amazon Redshift is `based on` open standard `PostgreSQL`, so most ` existing SQL client` applications will work with only minimal changes.

    - the `client` applications of Amazon redshift interacts using `two drivers`
    - These are standard interfaces that enable applications to interact with databases.
    
      - **JDBC**
        - In the context of Amazon Redshift, you can use JDBC to establish a connection to your Redshift cluster and perform various database operations using Java. 

        - **ODBC**
         - ODBC allows a user(directly from any application) to interact with live data of Amazon Redshift.

        - (In the case of Amazon Redshift, you can use ODBC to connect to your Redshift cluster from applications written in languages other than Java.)


- `Clusters`

    - A cluster is composed of one or more `compute nodes`. 
    - If a cluster is `provisioned` with `two or more` compute nodes, an additional `leader node` coordinates the compute nodes and handles external communications.
    - Client application interacts directly only with the leader node.

    - **Leader node**
        - The leader node manages communications with client programs and all communication with compute nodes.
        - It parses and develops execution plans to carry out database operations.
        - Based on the execution plan, the leader node `compiles code`, `distributes` the complied code to the  `compute nodes` and `assigns` a p`ortion of the data` to `each compute node`.
        - The leader node `distributes SQL statements` to the `compute nodes` only when a `query references tables` that are `stored on the compute nodes.` All other queries run exclusively on the leader node. 

    - **Compute nodes**

        - The compute nodes `run the compiled code` and `send intermediate results` back to the `leader node` for `final aggregation`.

        - Each compute node has its own dedicated CPU and memeory,which are determined by the node type.

        - you can increase the compute capacity of cluster by increasing the number of nodes.


- `Redshift Managed Storage`

    - Data warehouse` data ` is `stored `in a `separate` storage tier `Redshift Managed Storage` (RMS).

    - RMS provides the ability to scale your storage to petabytes using` Amazon S3 storage`.

    
- `Node Slice`
    - A compute node is `partitioned` into `slices`.
    - Each slice is allocated a portion of the node's `memeory` and `disk space`, where it processes a portion of the workload assigned to the node.

    - the number of slices per node is determined by the node size of the cluster.

- `Databases`

- A cluster `contains` `one or more databases`.
- User data is stored on the `compute nodes` of the Redshift cluster.
- your `Sql client` communicates with the `leader node`, which in turn `coordinates` query run with the compute nodes.
- `Compute nodes` are responsible for processing queries and coordinating the execution of those queries.

## additional concepts in Amazon Redshift

- Column storage
    - columner storage
    - essential factor in optimizing query performance and resulting in quicker outputs.

- Compression
    - compression is a column-level operation which decreases storage requirements.


# practical 
