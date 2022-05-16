### Running the job in Databricks  
`dbx execute --cluster-id=0510-125423-hlu5t4s7 --job=dbx-demo-job --no-rebuild --no-package`  

- `dbx-demo-job` is the name of the job (defined in `.conf/deployment.yml`)  
- `cluster-id` is currently the test cluster that have the Azure Analytics log agent created to run the sample jobs.


### Searching logs in Azure Monitor

<pre>
SparkLoggingEvent_CL
| search "(sample Python job prepared for Azure monitor)"
</pre>