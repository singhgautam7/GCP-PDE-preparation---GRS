
# Google Professional Data Engineering(PDE) Certification Exam Preparation Guide

This guide is created for the preparation/revision for the [Google Professional Data Engineering certification exam](https://cloud.google.com/certification/data-engineer). 

---

## Important Links for preparation
- [Udemy - GCP Associate Cloud Engineer Course](https://www.udemy.com/course-dashboard-redirect/?course_id=3827154)
 	- Helped me to get** basic knowledge** about GCP
- [Udemy - Google Cloud Professional Data Engineer Certification Course by Ankit Mistry](https://www.udemy.com/course-dashboard-redirect/?course_id=4095980)
	- After the above course, this course helped me to **dive deeper in GCP** and helped understand the cloud platform with exam's point of view. 
	- The course se really detailed and I had no problems in understanding it in 2x speed as well.
- [Udemy - Google Cloud Professional Data Engineer - Get Certified Course by Dan Sullivan](https://www.udemy.com/course-dashboard-redirect/?course_id=3125272) 
	- This is what I used for quickly **revising my concepts** and also this helped gain some more insights about exam related questions
	- At the end of the course, there is a 2 hrs long **Mock Test** with 50 questions which helped me get into the mindset of giving the exam.
- [Practice Question Bank](https://www.passnexam.com/google/google-data-engineer) with more than 200 questions
 > Note: Even though the answers are mentioned here, some of the answers might be wrong. So Google the questions or discuss it with peers to be 100% sure of the right answer. 
- [Videos](https://www.youtube.com/watch?v=7UOX2R-xf8I&list=PLQMsfKRZZviSLraRoqXulcMKFvIXQkHdA) on how to solve the questions in PDE

---

## Contents
Even though you can find all the topics inside the _study material_ folder, the suggested sequence for studying is as follows:
 1. [Non-mandatory prerequisite(s)](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/tree/main/study_material/others)
	 - [Hadoop Ecosystem](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/others/hadoop.md)
	 - [AI ML terminologies](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/others/ai_ml_terminologies.md)
	 - [Other Important Terminologies](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/tree/main/study_material/others)
	 - [Miscellaneous Facts](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/others/misc.md)
 2. [Data Lifecycle](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_lifecycle.md)
 3. [Data Transfer](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_transfer.md)
	 - [Cloud Storage Transfer Tools](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_transfer.md#1-cloud-storage-transfer-tools)
	 - [Storage Transfer Service](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_transfer.md#1-cloud-storage-transfer-tools)
	 - [Transfer Appliances](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_transfer.md#3-transfer-appliances)
	 - [BigQuery Data Transfer Service](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_transfer.md#4-bigquery-data-transfer-service)
 4. [Storage](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md) 
	 - [Cloud Storage](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#cloud-storage)
	 - [DataStore](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#datastore)
	 - [FireStore](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#firestore)
	 - [Cloud SQL](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#cloud-sql)
	 - [Cloud Spanner](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#cloud-spanner)
	 - [Bigtable](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#bigtable)
	 - [BigQuery](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/storage.md#bigquery)
 5. [Data Processing and Pipelines](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md)
	 - [DataFlow](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#dataflow)
	 - [DataProc](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#dataproc)
	 - [Pub/Sub](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#pubsub)
	 - [Cloud Data Fusion](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#dataprep)
	 - [DataPrep](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#dataprep)
	 - [Cloud Composer](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#cloud-composer)
	 - [Cloud Functions](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#dataproc-vs-dataflow-vs-dataprep)
	 - [DataProc vs DataFlow vs DataPrep](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/data_processing_and_pipelines.md#dataproc-vs-dataflow-vs-dataprep)
 6. [Machine Learning in GCP](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/ai_ml.md)
	 - [Machine Learning Basics](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/ai_ml.md#machine-learning)
	 	- [Pre-Trained Models](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/ai_ml.md#machine-learning)
	 	- [Auto-ML](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/ai_ml.md#automl)
	- [Deployment](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/ai_ml.md#deployment)
 7. [Data Visualization](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/visualization.md) 
	 - [Data Lab](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/visualization.md#cloud-datalab)
	 - [Data Studio](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/visualization.md#data-studio)
 8. [Management](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/management.md)
	 - [IAM](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/management.md#identity-and-access-management-iam)
	 - [Stackdriver](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/management.md#stackdriver)
	 - [Cloud Deployment Manager](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/management.md#cloud-deployment-manager)
	 - [Data Catalog](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/study_material/management.md#data-catalog)

