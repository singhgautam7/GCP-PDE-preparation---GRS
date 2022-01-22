# DataProc
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
 - IAM - 
	 - Service accounts used with Cloud Dataproc must have Dataproc/Dataproc Worker role (or have all the permissions granted by Dataproc Worker role).
		 - Need permissions to read and write to Google Cloud Storage, and to write to Google Cloud Logging
