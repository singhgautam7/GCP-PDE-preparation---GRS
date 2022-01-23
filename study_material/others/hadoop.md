## Hadoop Framework
 - Data can no longer fit in memory on one machine (monolithic), so a new way of computing was devised using many computers to process the data (distributed). Such a group is called a cluster.
 - Hadoop is an open source distributed processing framework that manages data processing and storage for big data applications running in clustered systems.
 - It is comprised of three main components - 
	 - *Hadoop Distributed File System (HDFS)*: Each disk on a different machine in a cluster is comprised of 1 master node; the rest are data nodes. The **master node** manages the overall file system by storing the directory structure and metadata of the files. The **data nodes** physically store the data
	 - *Map-Reduce*: Parallel programming paradigm which allows for processing of huge amounts of data by running processes on multiple machines.
	 - *YARN- Yet Another Resource Negotiator*: Coordinates tasks running on the cluster and assigns new nodes in case of failure.

## Hadoop Ecosystem
An entire ecosystem of tools have emerged around Hadoop, which are *based on interacting with HDFS*. 
- **Hive**: Data warehouse software built o top of Hadoop that facilitates reading, writing, and managing large datasets residing in distributed storage using SQL-like queries (HiveQL).
- **Pig**: high level scripting language (Pig Latin) that enables writing complex data transformations. **(GCP alternative : Dataflow)**
- **Spark**: Framework for writing fast, distributed programs for data processing and analysis.
- **Hive**: Non-relational, NoSQL, column-oriented database management system that runs on top of HDFS. **(GCP alternative : BigTable)**
- **Kafka/Flink**: Batch/stream processing framework.
- **Beam**: Programming model to define and execute data processing pipelines, including ETL, batch and stream (continuous) processing. **(GCP alternative : Google Cloud Dataflow)**
- **Oozie**: Workflow scheduler system to manage Hadoop jobs.
- **Sqoop**: Transferring framework to transfer large amounts of data into HDFS from relational databases
