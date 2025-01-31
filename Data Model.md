Prometheus data is time series data that consists of a series of different types of samples. Each type of sample is identified by a metric name and associated labels.

### Metric Name
The general feature of a system that is measured (ex: total_http_requests).
#### Spec:
- ASCII letters, digits, underscores and colons.
- digits cannot be the first character.
- colons are reserved for user defined recording rules. They should not be used by exporters or direct instrumentation. (whatevery that means)
- regex: \[a-zA-Z_:]\[a-zA-Z0-9_:]*

### Metric Labels
A series of key(name) value pairs that are associated with a metric. Each metric label name identifies a particular dimension of a metric (ex: http requests using POST method to an /api/tracks path could be identified as {method=post, path=/api/tracks}).

### Spec:
- #### Label Names
	- ASCII letters, digits, and underscores.
	- digits cannot be the first character.
	- regex: \[a-zA-Z_]\[a-zA-Z0-9_]*
	- names beginning with double underscore are reserved for internal use
- #### Values
	- Any UNICODE character.

### Samples
In the actual time series data, each sample consists of:
- a float64 value (stores the metric data)
- a millisecond-precision timestamp
```
NOTE: Expiremental support also available for native histograms instead of just a simple float64
```


### Notation
Here is how metrics are generally notated
```
<metric name>{<label_name>=<label value>, ...}
```
ex: A metric named total_http_requests for posts to the /api/tracks path could look like this:
```
total_http_requests{method="post", path="/api/tracks"}
```
