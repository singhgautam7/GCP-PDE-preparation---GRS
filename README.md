
# Google Professional Data Engineering(PDE) Certification Exam Preparation Guide

This guide is created for the preparation/revision for the [Google Professional Data Engineering certification exam](https://cloud.google.com/certification/data-engineer). 
I have tried to divide the topics into sections for better understanding and topic-specific revisions.

## Contents
Even though you can find all the topics inside the _study material_ folder, the suggested sequence for studying is as follows:
 1. [Data Lifecycle](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_lifecycle.md)
 2. [Data Transfer](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_transfer.md)
	 - Contents: 
		 - [Cloud Storage Transfer Tools](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_transfer.md#1-cloud-storage-transfer-tools)
		 - [Storage Transfer Service](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_transfer.md#1-cloud-storage-transfer-tools)
		 - [Transfer Appliances](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_transfer.md#3-transfer-appliances)
		 - [BigQuery Data Transfer Service](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_transfer.md#4-bigquery-data-transfer-service)
 3. [Storage](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md)
	 - Non-mandatory prerequisite(s):
		 - [Hadoop Ecosystem](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/others/hadoop.md)
	 - Contents: 
		 - [Cloud Storage](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#cloud-storage)
		 - [DataStore](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#datastore)
		 - [FireStore](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#firestore)
		 - [Cloud SQL](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#cloud-sql)
		 - [Cloud Spanner](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#cloud-spanner)
		 - [Bigtable](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#bigtable)
		 - [BigQuery](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#bigquery)
 4. [Data Processing and Pipelines](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md)
	 - Contents: 
		 - [DataFlow](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#dataflow)
		 - [DataProc](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#dataproc)
		 - [Pub/Sub](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#pubsub)
		 - [Cloud Data Fusion](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#dataprep)
		 - [DataPrep](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#dataprep)
		 - [Cloud Composer](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#cloud-composer)
		 - [Cloud Functions](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#dataproc-vs-dataflow-vs-dataprep)
		 - [DataProc vs DataFlow vs DataPrep](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#dataproc-vs-dataflow-vs-dataprep)
 5. [Machine Learning in GCP](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/ai_ml.md)
	 - Non-mandatory prerequisite(s):
		 - [AI ML terminologies](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/others/ai_ml_terminologies.md)
 6. [Data Visualization](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/visualization.md)
	 - Contents: 
		 - [Data Lab](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/visualization.md#cloud-datalab)
		 - [Data Studio](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/visualization.md#data-studio)
 7. [Management](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/management.md)
	 - Contents: 
		 - [IAM](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/management.md#identity-and-access-management-iam)
		 - [Stackdriver](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/management.md#stackdriver)
		 - [Cloud Deployment Manager](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/management.md#cloud-deployment-manager)
		 - [Data Catalog](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/management.md#data-catalog)
 8. [Extras](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/tree/main/study_material/others)

## Important Links
 - [Practice Question Bank](https://www.passnexam.com/google/google-data-engineer) with more than 200 questions
 > Note: Even though the answers are mentioned here, some of the answers might be wrong. So Google the questions or discuss it with peers to be 100% sure of the right answer. 
 - [Videos](https://www.youtube.com/watch?v=7UOX2R-xf8I&list=PLQMsfKRZZviSLraRoqXulcMKFvIXQkHdA) on how to solve the questions in PDE
