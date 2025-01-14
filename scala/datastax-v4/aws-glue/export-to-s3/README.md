## Using Glue Export Example
This example provides scala script for exporting Amazon Keyspaces table data to S3 using AWS Glue. This allows you to export data from Amazon Keyspaces without setting up a spark cluster.

## Prerequisites
* Setup Spark Cassandra connector using provided [setup script](../)

### Setup Export to S3
The following script sets up AWS Glue job to export a Keyspaces table to S3. The script takes the following parameters 
* KEYSPACE_NAME and TABLE_NAME Keyspaces and table is the fully qualified name of the table you wish to export. 
* PARENT_STACK_NAME is the stack name used to create the spark cassandra connector with Glue. [setup script](../)
* FORMAT can be json, csv, or parquet. parquet is recommended for ease of use with data loading, transformations, and using exports with Athena.

```shell
./setup PARENT_STACK_NAME KEYSPACE_TABLE TABLE_NAME FORMAT

```

By default the export will copy data to S3 bucket specified in the parent stack in the format ```/export/keyspace/table/``` . 
