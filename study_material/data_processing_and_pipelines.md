# Data Processing / Data Pipelines

## Dataflow
You can refer to [this](https://cloud.google.com/dataflow) for docs.
 - Cloud version for *Apache Beam*.
 - Process batch or stream data.
 - Serverless, fast, scalable, fault-tolerant.
 - Multi-Step processing data. Eg: Wordcount.
 - Used for data processing, ELT(Extract Transform Load), filter, group for data sets.
 - Can read data from multiple sources, can kick off multiple cloud functions in parallel and can also writer to multiple sinks (like BigQuery, BigTable etc.)
 - An example of dataflow can be seen in the following image: 
![Google Stream Analysis](https://www.gstatic.com/bricks/image/f4f99d139d05057c917bb62406d1c36ab2f297d945f9c7d340208211dc217d19.svg)
 - Jobs can be created with inbuilt templates, or notebook instances(write jobs in Java/Python/SQL)
 - Can apply [windowing](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/references/windowing.md) to streams for rolling average for the window, max in a window etc.
 - Triggers determines when a Window's contents should be output based on certain criteria being met. Types of triggers are :  
	 - Time based triggers
	 - Data Driven triggers
	 - Composite triggers
 - Important IAM roles - 
	 - **dataflow.developer** role enable the developer interacting with the Cloud Dataflow job , with data privacy. 
	 - **dataflow.worker** role provides the permissions necessary for a *Compute Engine service account* to execute work units for a Dataflow pipeline

## DataProc
You can refer to [this](https://cloud.google.com/dataproc/) for docs.
 - Dataproc is managed (No Ops) Hadoop cluster on GCP (i.e. managed Hadoop, Pig, Hive, Spark programs)
 - Lift and Shift existing Spark/Hadoop jobs is possible
 - Automated cluster management
 - Cluster types - 
	 - Standard (1 master, N workers)
	 - Single Node (1 master, 0 workers)
	 - High Availability (3 master, N workers)
 - Worker node can be a regular VM or a Preemptible VM.
 - Job Supported - Hadoop, SparkR, Spark, SparkSQL, Hive, Pig, PySpark
 - Can store data on disk (HDFS) or can use GCS
 - Google recommends using Cloud Storage instead of HDFS as it is much more cost effective especially when jobs aren’t running.
 - IAM - 
	 - Service accounts used with Cloud Dataproc must have Dataproc/Dataproc Worker role (or have all the permissions granted by Dataproc Worker role).
		 - Need permissions to read and write to Google Cloud Storage, and to write to Google Cloud Logging

## Pub/Sub
You can refer to [this](https://cloud.google.com/pubsub/docs/overview) for docs.
 - Serverless messaging
 - Order of message not guaranteed
 - Async processing
 - Messages are persisted in message store until they are delivered and acknowledged by subscribers
 - When message is ack, it is removed from subscription's message queue
 - How to Deduplicate: 
	 - Duplicates can happen when endpoint is not acknowledging messages.
	 - Maintain a DB to store hash value for each entry.
	 - Pub/Sub assigns a unique `message_id` to each message which can be used to detect duplicates.
 - Use cases : 
	 - Gather events from many clients simultaneously and use stream processing (like dataflow to deliver it to BigQuery, BigTable, CloudStorage on other DBs.
	 - Replicating data among DBs
	 - Parallel processing by Pub/Sub messages to connect to cloud functions.
	 - Data streaming for IOT devices.
	 - Cache invalidation for distributed cashes by publishing events.
	 - Load balancing for reliability.

## Data Fusion
You can refer to [this](https://cloud.google.com/data-fusion) for docs.
 - Code-free, drag and drop tool to quickly build data pipelines.

## DataPrep
You can refer to [this](https://cloud.google.com/dataprep/docs/how-to) for docs.
 - Service for visually exploring, cleaning, and preparing data for analysis. can transform data of any size stored in CSV, JSON, or relational table formats
 - Build by Trifacta – Third Party tool, not cloud native one
 - Dataprep is serverless and works at any scale
 - No code required
 - No infrastructure to deploy or manage
 - Automatically detect schema, anomalies

## Cloud Composer
You can refer to [this](https://cloud.google.com/composer/docs) for docs.
 - Fully managed *Apache Airflow* in google cloud
 - Helps you create, schedule, monitor and manage workflows
 - Workflows are defined as DAG (Direct Acyclic Graphs) which are written in Python 3.x
 - This also has built-in support for other GCP services like Pub?sub, Cloud Storage, DataFlow, DataProc

## Cloud Functions
You can refer to [this](https://cloud.google.com/functions/docs) for docs.
- No ops, no server just code entry point and response, auto-scaled by GCP
- Can be triggered by dataflow, GCS bucket events, Pub/Sub Messages and HTTP Calls
