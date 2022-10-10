# Compute Stack

## Google Compute Engine (GCE) — IaaS
- Infrastructure as a Service
- Virtual Machines (VMs) running in Google’s global data center. 
- You have the liberty of creating Virtual Machines, allocating CPU and Memory, Kind of Storage e.g. SSD or HDD, as well as the amount of storage
- Ideal for when you need complete control over your infrastructure and direct access to high-performance hardware or need OS-level changes.
- Use Cases: 
	- any workload requiring a specific OS or OS configuration
	- currently deployed and on-premises software that you want to run in the cloud.

## Google Kubernetes Engine (GKE) — (CaaS)
- Container as a Service
- Logical infrastructure powered by Kubernetes, an open-source container orchestration system. 
- Allows customers to easily run their Docker containers in a fully managed Kubernetes environment
- Ideal for managing containers in production, increase velocity and operability, and don’t have OS dependencies. 
- Use Cases: 
	- containerized workloads
	- cloud-native distributed systems
	- hybrid applications.

## Google App Engine (GAE) — (PaaS)
- Platform as a Service
- Flexible, serverless platform for building highly available applications.
- Ideal when you want to focus on writing and developing code and do not want to manage servers, clusters, or infrastructures. 
- Customers that use GAE do not have to deal with the underlying hardware/middleware but can already have a pre-configured platform ready to go; all they need to do is provide the necessary code required to run it
- Use Cases:
	- web sites
	- mobile app and gaming backends
	- RESTful APIs
	- IoT apps

## Google Cloud Functions — (FaaS)
- Function as a Service
- No ops, no server just code entry point and response, auto-scaled by GCP
- Can be triggered by dataflow, GCS bucket events, Pub/Sub Messages and HTTP Calls
- Cloud Functions is a managed serverless product that is able to respond to events in the cloud, such as creating a file in Cloud Storage
- The `--max-instances` parameter limits the number of concurrently executing function instances

## Comparison in Compute Services provided by GCP
![enter image description here](https://storage.googleapis.com/gweb-cloudblog-publish/images/GCP2Bcompute2Bservice2Bladder51qi.max-1200x1200.PNG)

## Important links
- [App Engine vs Cloud Run](https://dev.to/pcraig3/cloud-run-vs-app-engine-a-head-to-head-comparison-using-facts-and-science-1225)
