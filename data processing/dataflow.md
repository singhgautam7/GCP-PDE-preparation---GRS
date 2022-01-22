# Dataflow
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
