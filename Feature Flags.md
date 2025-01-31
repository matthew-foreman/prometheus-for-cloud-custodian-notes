This is a non-exhaustive list of [feature flags](https://prometheus.io/docs/prometheus/latest/feature_flags) prometheus has. I'm just noting the ones that seem interesting to possible use. Some we'll probably use. I have noted those that I want to use with *enable*. In order to enable them, the prometheus server is run as an --enable-feature=<feature_name> parameter.
- --
### Extra Scrape Metrics
- enable
- feature_name: extra-scrape-metrics
- more target related metrics that expose scrape config values and other metrics related to each scrape.
### Memory Snapshot on Shutdown
- enable
- feature_name: memory-snapshot-on-shutdown
#### Exemplar Storage
- --enable-feature=exemplar-storage
- exemplars are references to data outside of the metric set (ex: jaeger-trace-id)
- a fixed size circular buffer in memory for all series.
- exemplars will also be appended to WAL for local persistence. (for WAL duration)
- uses a config file block storage/exemplars to control the memory size by the number of exemplars
- size of the exemplar depends on which type it is
