As I'm learning about prometheus for use in cloud custodian, some different bits of technology and ideas are popping up. Here's where I'm managing those.



## [Prom-migrator](https://github.com/timescale/promscale/tree/master/migration-tool/cmd/prom-migrator)
Used to migrate prometheus data from one storage system to another (for backup or whatevs).


## [Prometheus AWS Timestream Adapter](https://github.com/dpattmann/prometheus-timestream-adapter)
This adapter could be run as a service for reading to and writing to AWS Timestream. 
Possible uses:
- a way back up prometheus data (could use the prom-migrator as a middle-man)
- a way to integrate other timestream data (perhaps the Hotshot project?).