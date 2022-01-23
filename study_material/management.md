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

## Stackdriver - 
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
- Application Performance Management (APM) combines the monitoring and troubleshooting capabilities of Cloud Logging and Cloud Monitoring
- Use cases - 
	- Monitor your infrastructure
	- Troubleshoot your applications
	- Health check monitoring
	- Latency management
	- Debugging by inspecting the state of your application at any code location in production without stopping or slowing down your requests
	- Security Management - provides near real-time user activity visibility across Google Cloud

## Data Studio
- Business Intelligence tool from Google
- Completely free
- Drag & drop, no code
- Connect your data from spreadsheets, Analytics, Google Ads, Google BigQuery and many more connectors
- Create reports & Dashboards
- Prefetch cache - 
	- You can turn the prefetch cache on, if you are using a data source that incurs usage costs (e.g., BigQuery) and want to minimize those costs
	- You can turn the prefetch cache off for a given report, if your data changes frequently and you want to prioritize freshness over performance

## Cloud Deployment Manager
- Allows you to specify all the resources needed for your application in a declarative format using yaml

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