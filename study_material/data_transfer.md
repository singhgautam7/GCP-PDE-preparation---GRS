# Data Transfer

All the sub-headings here represents approaches to data transfer.

## 1. Cloud Storage transfer tools

 - Upload data directly from computer to Cloud Storage.
 - For transfers up to few TBs.
 - Methods: 
	 - [Cloud Console UI](https://cloud.google.com/storage/docs/cloud-console#_uploadingdata) (Uploading data to bucket)
	 - [JSON API](https://cloud.google.com/storage/docs/json_api)
	 - [gsutil command line interface](https://cloud.google.com/storage/docs/quickstart-gsutil#upload_an_object_into_your_bucket) (parallel/multi-processing)


## 2. Storage Transfer Service

 - Quickly import online data into Cloud Storage from **other clouds**, from **on-premises** sources, or from **one bucket to another** within Google Cloud. Ex: Amazon s3, Azure Blob Storage
 - Set up recurring transfer jobs.
 - A managed solution which handles retries and provides detailed transfer logging.
 - The on-premise transfer service minimizes the transfer time by utilizing the maximum available bandwidth and by applying performance optimizations
 - Compressing and combining smaller files info fewer larger files is also a best practice for speeding up transfer speeds

| Transfer Scenario | Recommendation |
|--|--|
| Transferring from another cloud storage provider | Use Storage Transfer Service |
| Transferring less than 1 TB from on-premises | Use gsutil |
| Transferring more than 1 TB from on-premises | Use Transfer Service for on-premise data |
| Transferring less than 1 TB from another Cloud Storage region | Use gsutil |
| Transferring more than 1 TB from another Cloud Storage region | Use Storage Transfer Service |


## 3. Transfer Appliances
- Great option to migrate a large dataset and don’t have lots of bandwidth to spare
- Transfer Appliance enables seamless, secure, and speedy data transfer to Google Cloud
- For example, a 1 PB data transfer can be completed in just over 40 days using the Transfer Appliance, as compared the three years it would take to complete an online data transfer over a typical network (100 Mbps)
- Transfer appliance is highly performant because it uses all solid state drives

## 4. BigQuery Data Transfer Service
- Used to lay the foundation for a BigQuery data warehouse without writing a single line of code
- It automates data movement into BigQuery on a scheduled, managed basis
- It supports several [third-party sources](https://cloud.google.com/bigquery-transfer/docs/introduction#supported_data_sources) along with transfers from Google SaaS apps, external cloud storage providers. and data warehouses such as Teradata and Amazon Redshift

![enter image description here](https://storage.googleapis.com/gweb-cloudblog-publish/images/Data-Transfer-Service_v03-30-21.max-2000x2000.jpeg)
- 
