### Running the job in Databricks  
`dbx execute --cluster-id=0510-125423-hlu5t4s7 --job=dbx-demo-job --no-rebuild --no-package`  

- `dbx-demo-job` is the name of the job (defined in `.conf/deployment.yml`)  
- `cluster-id` is currently the test cluster that have the Azure Analytics log agent created to run the sample jobs.


### Searching logs in Azure Monitor

<pre>
SparkLoggingEvent_CL
| search "(sample Python job prepared for Azure monitor)"
</pre>  

or

<pre>
SparkLoggingEvent_CL
| where logger_name_s == "dbx-demo_logger" 
| project TimeGenerated, Message
</pre>

You can find more examples on how to query AZ Monitor by following the link below:  
https://docs.microsoft.com/en-us/azure/azure-monitor/logs/basic-logs-query?tabs=portal-1