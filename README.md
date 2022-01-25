# Google Professional Data Engineering(PDE) Certification Exam Preparation Guide

This guide is created for the preparation/revision for the Google Professional Data Engineering certification exam. 
I have tried to divide the topics into sections for better understanding and topic-specific revisions.

Even though you can find all the topics inside the `study material` folder, the suggested sequence for studying is as follows:
 1. [Data Lifecycle](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_lifecycle.md)
 2. [Storage](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md)
	 - [Hadoop Ecosystem](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/others/hadoop.md)
 3. [Data Processing and Pipelines](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md)
 4. [Machine Learning in GCP](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/ai_ml.md)
	 - [Tensor flow terminologies](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/others/tensorflow_terminology.md)
 5. [Data Visualization](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/visualization.md)
 6. [Management](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/management.md)

Link for question banks-
 - [Question Answer List in Google docs](https://docs.google.com/document/d/1hoMYLQDJsQ5etWUmyjrtOH91pJk2SZSkYJ_n8qEis8o/edit?usp=drivesdk)
 - [Practice Questions](https://www.passnexam.com/google/google-data-engineer)

## Exam Topics
#### Section 1. Designing data processing systems

1.1 Selecting the appropriate storage technologies. Considerations include:

-   Mapping storage systems to business requirements
-   Data modeling
-   Trade-offs involving latency, throughput, transactions
-   Distributed systems
-   Schema design

1.2 Designing data pipelines. Considerations include:

-   Data publishing and visualization (e.g., BigQuery)
-   Batch and streaming data (e.g., Dataflow, Dataproc, Apache Beam, Apache Spark and Hadoop ecosystem, Pub/Sub, Apache Kafka)
-   Online (interactive) vs. batch predictions
-   Job automation and orchestration (e.g., Cloud Composer)

1.3 Designing a data processing solution. Considerations include:

-   Choice of infrastructure
-   System availability and fault tolerance
-   Use of distributed systems
-   Capacity planning
-   Hybrid cloud and edge computing
-   Architecture options (e.g., message brokers, message queues, middleware, service-oriented architecture, serverless functions)
-   At least once, in-order, and exactly once, etc., event processing

1.4 Migrating data warehousing and data processing. Considerations include:

-   Awareness of current state and how to migrate a design to a future state
-   Migrating from on-premises to cloud (Data Transfer Service, Transfer Appliance, Cloud Networking)
-   Validating a migration

#### Section 2. Building and operationalizing data processing systems

2.1 Building and operationalizing storage systems. Considerations include:

-   Effective use of managed services (Cloud Bigtable, Cloud Spanner, Cloud SQL, BigQuery, Cloud Storage, Datastore, Memorystore)
-   Storage costs and performance
-   Life cycle management of data

2.2 Building and operationalizing pipelines. Considerations include:

-   Data cleansing
-   Batch and streaming
-   Transformation
-   Data acquisition and import
-   Integrating with new data sources

2.3 Building and operationalizing processing infrastructure. Considerations include:

-   Provisioning resources
-   Monitoring pipelines
-   Adjusting pipelines
-   Testing and quality control

#### Section 3. Operationalizing machine learning models

3.1 Leveraging pre-built ML models as a service. Considerations include:

-   ML APIs (e.g., Vision API, Speech API)
-   Customizing ML APIs (e.g., AutoML Vision, Auto ML text)
-   Conversational experiences (e.g., Dialogflow)

3.2 Deploying an ML pipeline. Considerations include:

-   Ingesting appropriate data
-   Retraining of machine learning models (AI Platform Prediction and Training, BigQuery ML, Kubeflow, Spark ML)
-   Continuous evaluation

3.3 Choosing the appropriate training and serving infrastructure. Considerations include:

-   Distributed vs. single machine
-   Use of edge compute
-   Hardware accelerators (e.g., GPU, TPU)

3.4 Measuring, monitoring, and troubleshooting machine learning models. Considerations include:

-   Machine learning terminology (e.g., features, labels, models, regression, classification, recommendation, supervised and unsupervised learning, evaluation metrics)
-   Impact of dependencies of machine learning models
-   Common sources of error (e.g., assumptions about data)

#### Section4. Ensuring solution quality

4.1 Designing for security and compliance. Considerations include:

-   Identity and access management (e.g., Cloud IAM)
-   Data security (encryption, key management)
-   Ensuring privacy (e.g., Data Loss Prevention API)
-   Legal compliance (e.g., Health Insurance Portability and Accountability Act (HIPAA), Children's Online Privacy Protection Act (COPPA), FedRAMP, General Data Protection Regulation (GDPR))

4.2 Ensuring scalability and efficiency. Considerations include:

-   Building and running test suites
-   Pipeline monitoring (e.g., Cloud Monitoring)
-   Assessing, troubleshooting, and improving data representations and data processing infrastructure
-   Resizing and autoscaling resources

4.3 Ensuring reliability and fidelity. Considerations include:

-   Performing data preparation and quality control (e.g., Dataprep)
-   Verification and monitoring
-   Planning, executing, and stress testing data recovery (fault tolerance, rerunning failed jobs, performing retrospective re-analysis)
-   Choosing between ACID, idempotent, eventually consistent requirements

4.4 Ensuring flexibility and portability. Considerations include:

-   Mapping to current and future business requirements
-   Designing for data and application portability (e.g., multicloud, data residency requirements)
-   Data staging, cataloging, and discovery
