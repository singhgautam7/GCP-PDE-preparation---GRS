# Management

## Identity and Access Management (IAM)
- Types of accounts - 
	- *Service Accounts* are for non human users such as applications
	- *Google Accounts* are for single users
	- *Google groups* are for multi users
- Billing - 
	- Billing access can be provided to a project or set of projects without granting access to the content
	- This is useful for separation of duties between finance/developers etc.
- Roles - 
```
TYPES OF ROLES
├── Primitive
│   ├── Owner
│   ├── Editor
│   ├── Viewer
│
├── Pre-defined (Examples below)
│   ├── Compute Admin
│   ├── Storage Viewer
│
├── Custom
│   ├── Combined collection of permissions
```

## Stackdriver
[Link](https://cloud.google.com/products/operations) to docs
- Now know as *Google Cloud's operations suite*
- For storing, searching, analyzing, monitoring, and alerts on log data and events.
- Sub-products are - 
	- Debugger
	- Error Reporting
	- Alerting
	- Trace
	- Logging
- **Audit Logs to review data access** (e.g. BigQuery)
- Application Performance Management (APM) combines the monitoring and troubleshooting capabilities of Cloud Logging and Cloud Monitoring without aggregated sink this will be required to be done for each project individually which will be cumbersome.
- Monitoring does not only provide you with access to Dataflow-related metrics, but also lets you to create alerting policies and dashboards so you can chart time series of metrics and choose to be notified when these metrics reach specified values.
- Use cases - 
	- Monitor your infrastructure
	- Troubleshoot your applications
	- Health check monitoring
	- Latency management
	- Debugging by inspecting the state of your application at any code location in production without stopping or slowing down your requests
	- Security Management - provides near real-time user activity visibility across Google Cloud
### Cloud Logging
- Stores log for 30 days
- Bigtable is not a sink option here.
- There is no way to create an alert on Cloud Logging not receiving data from a service

### Cloud Monitoring
- Create dashboards and visualizations
- Collect metrics from GCP, AWS and hybrid resources
- **Alerting** and Anamoly reporting

## Cloud Deployment Manager
- Allows you to specify all the resources needed for your application in a declarative format using yaml

## Data Catalog
- Cloud Catalog is designed to help data consumers understand what data is available, what it means, and how it can be used
- A fully managed and highly scalable data discovery and metadata management service
- Single place to discover all data, asset across all project
- Use cases - Search and tag data
- Data Catalog will collect metadata automatically from several GCP sources. These sources include Cloud Storage, Cloud Bigtable, Google Sheets, BigQuery, and Cloud Pub/Sub.
- In addition to native metadata, Data Catalog can collect custom  metadata through the use of tags

## Data transfer
- Storage Transfer Service - 
	- For cloud data - 	
		- Transfer data from online sources like AWS S3 and Azure Blob Storage to Cloud Storage in one simple process
	- For on-premise data - 
		- Transfer petabytes of data from on-premises sources to Cloud Storage over online networks.
- Transfer Appliance - 
	- one-time - Rack, capture and then ship your offline data to Google Cloud
- If you have a large number of files to transfer you might want to use the gsutil -m option, to perform a parallel (multi-threaded/multi-processing)
- Compressing and combining smaller files info fewer larger files is also a best practice for speeding up transfer speeds
![enter image description here](https://storage.googleapis.com/gweb-cloudblog-publish/images/Data-Transfer-Service_v03-30-21.max-2000x2000.jpeg)
