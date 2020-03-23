# sf-crime
Crime Statistics Project for Udacity Data Streaming project

**1. How did changing values on the SparkSession property parameters affect the throughput and latency of the data?**

On example here is the parameter processedRowsPerSecond. With this parameter we can tune the settings and allow higher performance per second.

**2. What were the 2-3 most efficient SparkSession property key/value pairs? Through testing multiple variations on values, how can you tell these were the most optimal?**

In general and what has been described in the question one, the performance increase is at the heart of the optimisation. To optimize this the following parameters are key and therefore need to get modified to increase performance.

- spark.default.parallelism  // With this we can ensure that we parallelize to all CPUs which we can use
- spark.streaming.kafka.maxRatePerPartition // Here we can define limits to ensure the Partitions stay in a stable mode
- spark.sql.shuffle.partitions  // Limitation of shuffles which are created in group or join operations
