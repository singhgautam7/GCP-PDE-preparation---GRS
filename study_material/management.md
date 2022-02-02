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
- **Audit Logs to review data access** (e.g. BigQuery)
- Application Performance Management (APM) combines the monitoring and troubleshooting capabilities of Cloud Logging and Cloud Monitoring without aggregated sink this will be required to be done for each project individually which will be cumbersome.
- Monitoring does not only provide you with access to Dataflow-related metrics, but also lets you to create alerting policies and dashboards so you can chart time series of metrics and choose to be notified when these metrics reach specified values.
- Use cases - 
	- **Debugger**: inspect state of app in real time without stopping/slowing down e.g. code behavior
	- **Error Reporting**: counts, analyzes, aggregates crashes in cloud services
	- **Monitoring**: overview of performance, uptime and heath of cloud services (metrics, events, metadata)
	- **Alerting**: create policies to notify you when health and uptime check results exceed a certain limit
	- **Tracing**: tracks how requests propagate through applications/receive near real-time performance results, latency reports of VMs
	- **Logging**: store, search, monitor and analyze log data and events from GCP
#### Cloud Logging
- Stores log for 30 days
- Bigtable is not a sink option here.
- There is no way to create an alert on Cloud Logging not receiving data from a service

#### Cloud Monitoring
- Create dashboards and visualizations
- Collect metrics from GCP, AWS and hybrid resources
- **Alerting** and Anamoly reporting

#### Components Use-Cases
| Component | Used for |
|--|--|
| Stackdriver Logging | Collect semi-structured data about events |
| Stackdriver Debugger | Inspect the state of running code |
| Stackdriver Monitoring | Collects performance metrics |
| Stackdriver Trace | Collect information about the time required to execute functions in a call stack |

## Cloud Deployment Manager
- Allows you to specify all the resources needed for your application in a declarative format using yaml

## Data Catalog
- Cloud Catalog is designed to help data consumers understand what data is available, what it means, and how it can be used
- A fully managed and highly scalable data discovery and metadata management service
- Single place to discover all data, asset across all project
- Use cases - Search and tag data
- Data Catalog will collect metadata automatically from several GCP sources. These sources include Cloud Storage, Cloud Bigtable, Google Sheets, BigQuery, and Cloud Pub/Sub.
- In addition to native metadata, Data Catalog can collect custom  metadata through the use of tags
