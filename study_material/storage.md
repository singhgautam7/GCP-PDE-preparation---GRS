# Storage and Databases

![Types of storage](https://cloud.google.com/architecture/images/data-lifecycle-3.svg)

## Cloud Storage
 - It is a bucket, or we can call it a blob storage - similar to *Amazon S3
 - The content is not indexed at all.
 - No capacity or planning required. Almost unlimited storage.
 - Can be accessed by http(s) or REST APIs.
 - Multi-region or Dual-region also supported
 - Access control can be *uniform* or *fine-grained*
 - Object versioning and retention policy also supported.
 - A regional Google Cloud Storage is cheaper.
 - Types of storage:
	 - Standard (accessed frequently)
	 - Nearline (accessed once a month)
	 - Coldline (accessed once a quarter)
	 - Archive (accessed once a year)
 - On basis of conditions and actions, lifecycle of all objects in the bucket can be controlled
 - gsutil command used in shell.
 - The data here can be commonly used by Dataproc and BigQuery
 - *Signed URL*:
	 - Temporary access for a person with or without google account.
	 - Max limit = 10 days
	 - Access can be given **for objects** using signed url.

## DataStore
 - NoSQL DB, serverless, highly scalable
 - AutoScale supported.
 - High availability of reads and writes.
 - Fully managed with no planned downtime
 - It is a fully managed and serverless solution that allows for transactions and will autoscale (storage and compute) without the need to manage any infrastructure
 - Each transaction is guaranteed to be **atomic**, meaning that transactions are never partially applied. Either all of the operations in the transaction are applied, or none of them are applied.
 - Document kind storage
 - Tightly coupled with app engine, so one project can have jusgt one firestore/datastore
 - GQL (Google Query Language) is used which is similar to SQL
 - Support ACID (Atomicity, Consistency, Isolation, Durability) transactions
 - Replication across different regions is possible
 - Export is only available with gcloud utility only.

|DataStore|RDBMS|
|:-:|:-:|
|Kind|Table|
|Key|PK|
|Entity|Row|
|Property|Column|

## FireStore
 - Only datastore or firestore can be used in a project
 - It is next gen datastore
 - Collection and document model used
 - Native mode = Firestore mode

|FireStore|RDBMS|
|:-:|:-:|
|Collection|Table|
|Document ID|PK|
|Document|Row|
|Field|Column|

![Which Storage Should I Use](https://storage.googleapis.com/gweb-cloudblog-publish/images/Storage-to-Use_v04-23-21.max-1600x1600.jpeg)

## Cloud SQL
- Fully managed
- Cannot be scaled globally
- Can connect to App engine, Google Kubernetes Engine or Compute Engine
- Can Store 30 TB of data
- Backups - 
	- On-Demand Backups
	- Scheduled Backups
- DB Migration Service (DMS) available
- To shift some workloads, `read replicas` can be made.

## Cloud Spanner
- Can be scaled globally.
- Costly.
- Use when data is > 2TB
- Lift and Shift not recommended for this.
- Spanner = SQL + Horizontal Scalability
- High replication possible

## SQL vs Spanner
Cloud Spanner is used when you need to handle massive amounts of data with an elevated level of consistency and with a big amount of data handling (+100,000 reads/write per second). Spanner gives much better scalability and better SLOs.

On the other hand, Spanner is also much more expensive than Cloud SQL.

If you just want to store some data of your customer in a cheap way but still don't want to face server configuration Cloud SQL is the right choice.

If you are planning to create a big product or if you want to be ready for a huge increase in users for your application (viral games/applications) Spanner is the right product

## Bigtable
Refer to this [link](https://cloud.google.com/bigtable/docs/overview) for doc.
- Stored on Google’s internal store Colossus 
- No transactional support (so can handle petabytes of data)
- Bigtable is a key/value store, not a relational store. It does not support joins, and transactions are supported only within a single row
- Each table has only one index, the row key, and each row key must be unique
	- Best practices of bigtable states that rowkey:
		- Should not be only timestamp 
		- Should not have timestamp at starting.
- Bigtable tables are sparse. A column doesn't take up any space in a row that doesn't use the column
- Data Replication: Replications is copying data across multiple regions to increase durability. Just add another cluster and it will be possible to replicate the data.
- No downtime for cluster resize
- Useful for: 
	- IOT data
	- Financial data
	- Graph data
	- Marketing data
- Mutations or Deletions takes extra storage as mutations are stored sequentially.
- Deletions are just specialized mutations.
- Automatic read-write operations to reorganize the data or to remove deleted items.
- A Cloud Bigtable instance is mostly just a container for your clusters and nodes, which do all of the real work.
- **Partitioning > Table Sharding**: When you have multiple wildcard tables, best option is to shard it into single partitioned table. Time and cost efficient
- Tables belong to instances, not to clusters or nodes. So if you have an instance with up to 2 clusters, you can't assign tables to individual clusters
- Security:
	- Access is given to Bigtable via IAM.
	- Can manage security at project, instance and table levels
- Backups are also supported.
- It does not support SQL queries, joins or multi-row transactions.
- Not good for data less than 1TB of data or items greater than 10MB.
- `cbt` is a tool for doing basic interactions with Cloud Bigtable
- Impossible to Switching between SSD and HDD
- [Garbage collection](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/others/definitions/garbage_collection.md) is supported.
- Supports max of 1,000 tables in each instance.
- Can use up to around 100 column families.
- Empty columns don’t take up any space. Can create large number of columns, even if most columns are empty in most rows
- Creating row keys- 
	- Design your row key based on the queries you will use to retrieve the data.
	- It's important to create a row key that makes it possible to retrieve a well-defined range of rows. Otherwise, your query requires a table scan, which is much slower than retrieving specific rows.
	- For example, if your application tracks mobile device data, you can have a row key that consists of device type, device ID, and the day the data is recorded. Row keys for this data might look like this:
		- `phone#4c410523#20200501`
		- `phone#4c410523#20200502`
		- `tablet#a0b81f74#20200501`
		- `tablet#a0b81f74#20200502`
	- This row key design lets you retrieve data with a single request for:
		- A device type
		- A combination of device type and device ID
	- This row key design would not be optimal if you want to retrieve all data for a given day. Because the day is stored in the third segment, or the row key suffix, you cannot just request a range of rows based on the suffix or a middle segment of the row key.
	- In many cases, you should design row keys that start with a common value and end with a granular value.
	- Avoid using a single row key to identify a value that must be updated very frequently
	- Hashing a row key removes your ability to take advantage of Bigtable's natural sorting order, making it impossible to store rows in a way that are optimal for querying

## BigQuery
Refer to this [link](https://cloud.google.com/bigquery/docs/introduction) for doc.
- Fully managed Data Warehouse
- Alternative to Hadoop with Hive
- Has connectors for BigTable, GCS, Google Drive and can import from Datastore backups, CSV, JSON and ARVO
- A serverless, analytical DB
- Uses SQL
- Zero infrastructure management
- Can query TB of data in seconds and PB of data in minutes
- Columnar storage
- Not for transactional purposes
- Can also query from external data sources like SQL, Bigtable
- Supports CSV, JSON, Avro, SQL
- Querying is very expensive here
- Command line tool = `bq`
- BigQuery is not suitable for transactional use case
- Hierarchy - 
```
├── Project
│   ├── Datasets
│   │   ├── Tables
│   │   │   ├── Data
│   │   │   ├── Jobs
```
- Tables here have schema
- Types of tables - 
	- Native tables
	- External tables (from external sources, also know as **federated** sources)
	- Views
- Jobs are async tasks that work on the top of table
- Used for load, query, extract or query data
- When to use - 
	- When workload is analytical
	- When the data does not change much in DB, since caching is also used in BigQuery
	- When complex queries needs to be run
	- Offload some work from primary DB to run time taking/complex queries
- No join is preferred in BigQuery
- The data should be denormalized
- Security can be applied at a project level or dataset level but NOT at table level.
- Authorized views allows to share query results without giving access to the underlying data
- Caching time = 24 hrs
- No prices from data fetched from cache.
- Wildcard tables - Used if you want to union all similar tables with similar names. ’*’ (e.g. project.dataset.Table*)
- Partitioning in BigQuery : Dividing a table into segments to make it easier to manage and query data. This saves cost and time. Partition is nothing but a newly created table.
	- Time Unit Column Partition - Based on timestamp, date or datetime col in a table. Special partitions are `__NULL__`(contains rows with null values in partitioning column) and `__UNPARTITIONED__`(value of partitioning column not in partitioning range)
	- Ingestion Time Partition - Partitioned by the time row was ingested in a table.
	- Integer Range Partition - Based on integer col of the table. Here we specify col name, start value, end value and interval. `__NULL__` and `__UNPARTITIONED__` are also created in this.
- Types of queries - 
	- Interactive: query is executed immediately
	- Batch: Batches of queries are queued and the query starts when idle resources are available
- Data Import -
	- Batch import - web console (local files), GCS, GDS
	- Stream - data with CDF, Cloud logging or POST calls
	- Raw files - federated data source, CSV/JSON/Avro on GCS, Google sheets
	- By default, the BigQuery service expects all source data to be UTF-8 encoded
	- To support (occasionally) schema changing we can use 'Automatically detect' for schema changes. Automatically detect is not default selected
- Data Export - 
	- Data can only be exported in JSON / CSV / Avro
	- To export more than 1 GB of data, you need to put a wildcard in the destination filename. (up to 1 GB of table data to a single file)
- BigQuery Data Transfer Service can only transfer data into BigQuery, not out of it
- You can load data into BigQuery via two options: batch loading (free) and streaming (costly).
- Controlling costs - 
	- Avoid SELECT * (full scan), select only columns needed (SELECT * EXCEPT)
	- Sample data using preview options for free
	- Preview queries to estimate costs (dryrun)
	- Use max bytes billed to limit query costs
	- Don’t use LIMIT clause to limit costs (still full scan)
	- Monitor costs using dashboards and audit logs
	- Partition data by date
	- Break query results into stages
	- Use default table expiration to delete unneeded data
	- Use streaming inserts wisely
	- Set hard limit on bytes (members) processed per day
- Query Performace: Generally, queries that do less work perform better.
	- Input Data/Data Sources
		- Avoid SELECT *
		- Prune partitioned queries (for time-partitioned table, use PARTITIONTIME pseudo column to filter partitions)
		- Denormalize data (use nested and repeated fields)
		- Use external data sources appropriately
		- Avoid excessive wildcard tables
	- SQL Anti-Patterns
		- Avoid self-joins., use window functions (perform calculations across many table rows related to current row)
		- Partition/Skew: avoid unequally sized partitions, or when a value occurs more often than any other value
		- Cross-Join: avoid joins that generate more outputs than inputs (pre-aggregate data or use window function) Update/Insert Single Row/Column: avoid point-specific DML, instead batch updates and inserts.
	- Optimizing Query Computation
		- Avoid repeatedly transforming data via SQL queries
		- Avoid JavaScript user-defined functions
		- Use approximate aggregation functions (approx count)
		- Order query operations to maximize performance. Use ORDER BY only in outermost query, push complex operations to end of the query.
		- For queries that join data from multiple tables, optimize join patterns. Start with the largest table.
- [Link](https://cloud.google.com/architecture/dw2bq/dw-bq-migration-overview) for Migrating data warehouses to BigQuery
- [Link](https://cloud.google.com/bigquery/docs/best-practices-performance-patterns) for Best practices for performance

## Choosing a Database
- If there is a requirement to search terabytes or petabytes of data relatively quickly it will make more sense to simply store in BigQuery.
- If the data set is relatively small < 10TB then DataStore will be preferred.
- If the data set is > 10TB and/or there is no requirement for multiple indexes then BigTable will be better.
- If searching for objects by attribute value is required, then Datastore is preferred.
- If high throughput writes of wide column data then Bigtable is preferred.
- If there is a need of data warehousing then BigQuery is preferred.

![enter image description here](https://juanignaciosl.github.io/img/deogcp-storage.png)

![enter image description here](https://storage.googleapis.com/gweb-cloudblog-publish/images/Which-Database_v07-10-21_1.max-2000x2000.jpeg)
