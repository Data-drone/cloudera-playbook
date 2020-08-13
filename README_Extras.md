# Extra Notes

Impala Port is hardcoded in hue.j2

need to set the safety valve to 21050 when TLS is not enabled for hue

CSP Parcel has mutiple parcels in the manifest that we need


We haven't fully locked down the cluster as per:
https://docs.cloudera.com/documentation/enterprise/5-16-x/topics/sg_sentry_service_config.html

things like preventing CLI access from users from in the hive / sentry / hue groups isn't done



### Extra Thoughts

Add my superuser group in?

need to add cm/allHosts/config PUT for SMM:

`http://<cm_host>:7180/api/v33/cm/allHosts/config`
```json

{
  "items" : [ {
    "name" : "host_agent_safety_valve",
    "value" : "kafka_broker_topic_partition_metrics_for_smm_enabled=true",
    "sensitive" : false
  } ]
}


```
