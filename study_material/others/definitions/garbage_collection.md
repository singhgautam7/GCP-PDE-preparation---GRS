## Garbage Collection

Garbage collection is the automatic, ongoing process of removing expired and obsolete data from Bigtable tables. A garbage collection policy is a set of rules you create that state when data in a specific column family is no longer needed.

Garbage collection is a built-in, asynchronous background process. It can take up to a week before data that is eligible for garbage collection is actually deleted. Garbage collection occurs on a fixed schedule that does not vary based on how much data needs to be deleted. Until the data is deleted, it appears in read results
