These are notes about prometheus related to the cloud custodian application.

### [Pushgateway](https://github.com/prometheus/pushgateway)
While researching this last month, I found an article recommending the pushgateway for Kubernetes CronJobs, since they are short-lived. The cloud custodian cron jobs would push to the push gateway, and the prometheus server would be configured to pull from it.