## Pub/Sub
You can refer to [this](https://cloud.google.com/pubsub/docs/overview) for docs.
 - Serverless messaging
 - Order of message not guaranteed
 - Async processing
 - Messages are persisted in message store until they are delivered and acknowledged by subscribers
 - When message is ack, it is removed from subscription's message queue
 - How to Deduplicate: 
	 - Duplicates can happen when endpoint is not acknowledging messages.
	 - Maintain a DB to store hash value for each entry.
	 - Pub/Sub assigns a unique `message_id` to each message which can be used to detect duplicates.
 - Use cases : 
	 - Gather events from many clients simultaneously and use stream processing (like [dataflow](https://github.com/singhgautam7/GCP-PDE-preparation---GRS/blob/main/data%20processing/dataflow.md)) to deliver it to BigQuery, BigTable, CloudStorage on other DBs.
	 - Replicating data among DBs
	 - Parallel processing by Pub/Sub messages to connect to cloud functions.
	 - Data streaming for IOT devices.
	 - Cache invalidation for distributed cashes by publishing events.
	 - Load balancing for reliability.
