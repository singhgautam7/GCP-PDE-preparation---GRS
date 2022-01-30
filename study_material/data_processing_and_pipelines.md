
# Data Processing / Data Pipelines

## Dataflow
You can refer to [this](https://cloud.google.com/dataflow) for docs.
 - Cloud version for *Apache Beam*.
 - Preferred for new Hadoop or Spark infrastructure development
 - Process batch or stream data.
 - Serverless, fast, scalable, fault-tolerant.
 - Multi-Step processing data. Eg: Wordcount.
 - Cloud dataflow executed as jobs where one or more worker carry out specific tasks
 - Supports SQL, Java, Python
 - Stackdriver integration for logging and monitoring
 - Used for data processing, ELT(Extract Transform Load), filter, group for data sets.
 - Can read data from multiple sources, can kick off multiple cloud functions in parallel and can also writer to multiple sinks (like BigQuery, BigTable etc.)
 - When you update a job on the Dataflow service, you replace the existing job with a new job that runs your updated pipeline code
 - An example of dataflow can be seen in the following image: 
![Google Stream Analysis](https://www.gstatic.com/bricks/image/f4f99d139d05057c917bb62406d1c36ab2f297d945f9c7d340208211dc217d19.svg)
 - Jobs can be created with inbuilt templates, or notebook instances(write jobs in Java/Python/SQL)
 - Can apply [windowing](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/others/definitions/windowing.md) to streams for rolling average for the window, max in a window etc.
 - You can stop a Dataflow job in the following two ways:
	- Canceling a job. This method applies to both streaming and batch pipelines. Canceling a job stops the Dataflow service from processing any data, including buffered data
	- Draining a job. This method applies only to streaming pipelines. Draining a job enables the Dataflow service to finish processing the buffered data while simultaneously ceasing the ingestion of new data.
 - Updating the pipeline: 
 	- If any major change to windowing transformation (like completely changing window fn from fixed to sliding) in Beam/Dataflow/you want to stop pipeline but want inflight data --> use Drain option.
	- For all other use cases and Minor changing to windowing fn (like just changing window time of sliding window) --> Use Update with Json mapping.
 - Important IAM roles - 
	 - **dataflow.developer** role enable the developer interacting with the Cloud Dataflow job , with data privacy. 
	 - **dataflow.worker** role provides the permissions necessary for a *Compute Engine service account* to execute work units for a Dataflow pipeline


 <details><summary>Common Concepts in Dataflow</summary>
<p>

- **Pipeline**: encapsulates series of computations that accepts input data from external sources, transforms data to provide some useful intelligence, and produce output
- **PCollections**: abstraction that represents a potentially distributed, multi-element data set, that acts as the pipeline’s data. PCollection objects represent input, intermediate, and output data. The edges of the pipeline.
- **Transforms**: operations in pipeline. A transform takes a PCollection(s) as input, performs an operation that you specify on each element in that collection, and produces a new output PCollection. Composite transforms are multiple transforms: combining, mapping, shuffling, reducing, or statistical analysis.
- **Pipeline I/O**: the source/sink, where the data flows in and out. Supports read and write transforms for a number of common data storage types, as well as custom.
- **Windowing**: Windowing a PCollection divides the elements into windows based on the associated event time for each element.
- **Triggers**: Allows specifying a trigger to control when (in processing time) results for the given window can be produced. Triggers determines when a Window's contents should be output based on certain criteria being met. Types of triggers are :  
	 - Time based triggers
	 - Data Driven triggers
	 - Composite triggers
- **Watermark**: It is a threshold that indicates when Dataflow expects all of the data in a window to have arrived. If new data arrives with a timestamp that's in the window but older than the watermark, the data is considered **late data**.
- **ParDo**: It is a parallel processing function which can transform elements of an input PCollection to an output PCollection.
- **DoFn**: It is a template which is used to create user defined functions that are referenced by ParDo
</p>
</details>

## DataProc
You can refer to [this](https://cloud.google.com/dataproc/) for docs.
 - Provides access to Hadoop cluster on GCP and Hadoop-ecosystem tools (Pig, Hive, and Spark).
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
 - Cloud Dataproc is the better option when migrating and existing Spark/Hadoop cluster to GCP. **New data pipelines should prefer Cloud Dataflow**.
 - Hadoop/Spark jobs are run on Dataproc, and the **pre-emptible machines cost 80% less**.
 - Dataproc **Graceful Decommissioning** incorporates Graceful Decommission of YARN Nodes to finish work in progress on a worker before it is removed from the Cloud Dataproc cluster. By default this is disabled. 
	- This make sures that the work in progress is not lost while scaling.
 - If you create a Dataproc cluster with internal IP addresses only, attempts to access the Internet in an initialization action will fail unless you have configured routes to direct the traffic through a NAT or a VPN gateway. Without access to the Internet, you can enable Private Google Access, and **place job dependencies in Cloud Storage**; cluster nodes can download the dependencies from Cloud Storage from internal IPs.
 - IAM - 
	 - Service accounts used with Cloud Dataproc must have Dataproc/Dataproc Worker role (or have all the permissions granted by Dataproc Worker role).
		 - Need permissions to read and write to Google Cloud Storage, and to write to Google Cloud Logging

## Pub/Sub
You can refer to [this](https://cloud.google.com/pubsub/docs/overview) for docs.
 - Replacement for **Kafka**
 - Serverless messaging
 - Order of message not guaranteed
 - Async processing
 - Messages are persisted in message store until they are delivered and acknowledged by subscribers
 - When message is ack, it is removed from subscription's message queue
 - The only scenario for real time is the use of pub/sub with push.
 - If messages exceed the 10MB maximum, they cannot be published.
 - If in exam it is writtern: "Delivery of confimed atleast 1 message" or "message must be delivered/processed atleast once" then go with the Pub/Sub option.
 - Pub sub can retain message only for 7 days maximum
 - It also integrates well with Cloud Dataflow
 - How to Deduplicate: 
	 - Duplicates can happen when endpoint is not acknowledging messages.
	 - Maintain a DB to store hash value for each entry.
	 - Pub/Sub assigns a unique `message_id` to each message which can be used to detect duplicates.
<details><summary>Use Cases of PubSub</summary>
<p>

1. Gather events from many clients simultaneously and use stream processing (like dataflow to deliver it to BigQuery, BigTable, CloudStorage on other DBs.
2. Replicating data among DBs
3. Parallel processing by Pub/Sub messages to connect to cloud functions.
4. Data streaming for  various processes or devices(ex- IOT devices).
5. Cache invalidation for distributed cashes by publishing events, i.e. refreshing caches.
6. Load balancing for reliability.
7. Implementing asynchronous workflows.
8. Distributing event notifications.
9. Logging to multiple systems.

</p>
</details>

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
 - Dataprep can be run on Dataflow using template and cloud composer

## Cloud Composer
You can refer to [this](https://cloud.google.com/composer/docs) for docs.
 - Fully managed *Apache Airflow* in google cloud
 - Helps you create, schedule, monitor and manage workflows
 - Workflows are defined as DAG (Direct Acyclic Graphs) which are written in Python 3.x
 - This also has built-in support for other GCP services like Pub/sub, Cloud Storage, DataFlow, DataProc
 - It serves well when orchestrating interdependent pipelines
 - Cloud Composer should be used when there is inter-dependencies between the job, e.g. we need the output of a job to start another whenever the first finished, and use dependencies coming from first job
 - All interdependent tasks need to be run through cloud composer whereas small/adhoc tasks need to be run via **cloud scheduler**.

## Cloud Functions
You can refer to [this](https://cloud.google.com/functions/docs) for docs.
- No ops, no server just code entry point and response, auto-scaled by GCP
- Can be triggered by dataflow, GCS bucket events, Pub/Sub Messages and HTTP Calls

## DataProc vs DataFlow vs DataPrep
![enter image description here](https://cloud.google.com/architecture/images/data-lifecycle-4.svg)

