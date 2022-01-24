# Exponential Backoff
It is a technique that retries an operation, with an exponentially increasing wait time, up to a maximum retry count has been reached. This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.\

### Why use it?
When devices retry calls without waiting, they can produce a heavy load on the Cloud IoT Core servers. Cloud IoT Core automatically limits projects that generate excessive load. Even a small fraction of overactive devices can trigger limits that affect all devices in the same Google Cloud project.
To avoid triggering these limits, it is strongly recommended implement truncated exponential backoff with introduced jitter.

### More details
Truncated exponential backoff is a standard error-handling strategy for network applications. In this approach, a client periodically retries a failed request with increasing delays between requests. Clients should use truncated exponential backoff for all requests to Cloud IoT Core that return HTTP 5xx and 429 response codes, as well as for disconnections from the MQTT server.
