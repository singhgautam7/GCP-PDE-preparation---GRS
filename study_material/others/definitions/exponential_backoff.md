# Exponential Backoff
It is a technique that retries an operation, with an exponentially increasing wait time, up to a maximum retry count has been reached. This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.\

### Why use it?
If your application attempts to connect to the database and does not succeed, the database could be temporarily unavailable. In this case, sending too many simultaneous connection requests might waste additional database resources and increase the time needed to recover. Using exponential backoff prevents your application from sending an unresponsive number of connection requests when it can't connect to the database.

This retry only makes sense when first connecting, or when first grabbing a connection from the pool. If errors happen in the middle of a transaction, the application must do the retrying, and it must retry from the beginning of a transaction. So even if your pool is configured properly, the application might still see errors if connections are lost.
To avoid triggering these limits, it is strongly recommended implement truncated exponential backoff with introduced jitter.

### More details
Truncated exponential backoff is a standard error-handling strategy for network applications. In this approach, a client periodically retries a failed request with increasing delays between requests. Clients should use truncated exponential backoff for all requests to Cloud IoT Core that return HTTP 5xx and 429 response codes, as well as for disconnections from the MQTT server.
