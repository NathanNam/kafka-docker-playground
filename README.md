<!-- omit in toc -->
# <img src="https://www.docker.com/sites/default/files/d8/2019-07/vertical-logo-monochromatic.png" width="24"> <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Apache_kafka.svg/1200px-Apache_kafka.svg.png" width="16"> <img src="https://avatars3.githubusercontent.com/u/9439498?s=60&v=4" width="24"> kafka-docker-playground

Playground for Kafka/Confluent Docker experimentations...

![Github CI](https://github.com/vdesabou/kafka-docker-playground/workflows/CI/badge.svg)![success tests](https://img.shields.io/badge/success%20tests-478%2F594-red)![connector tested](https://img.shields.io/badge/connector%20tested-113-green)![cp versions tested](https://img.shields.io/badge/cp%20version%20tested-%206.1.1%206.0.2%205.5.3-green)![last run](https://img.shields.io/badge/last%20run-2021--04--20%2006:05-green)
![GitHub issues by-label](https://img.shields.io/github/issues/vdesabou/kafka-docker-playground/bug%20🔥)![GitHub issues by-label](https://img.shields.io/github/issues/vdesabou/kafka-docker-playground/enhancement%20✨)
![GitHub repo size](https://img.shields.io/github/repo-size/vdesabou/kafka-docker-playground)

ℹ️ [How to run](https://github.com/vdesabou/kafka-docker-playground/wiki/How-to-run)

<!-- omit in toc -->
## Table of Contents

- [🔗 Kafka Connectors](#-kafka-connectors)
- [☁️ Confluent Cloud](#️-confluent-cloud)
  - [Confluent Cloud Demo](#confluent-cloud-demo)
  - [🔗 Kafka Connectors connected to Confluent Cloud](#-kafka-connectors-connected-to-confluent-cloud)
  - [Other](#other)
- [🔄 Confluent Replicator and Mirror Maker 2](#-confluent-replicator-and-mirror-maker-2)
- [🔐 Environments](#-environments)
- [Confluent Commercial](#confluent-commercial)
- [CP-Ansible Playground](#cp-ansible-playground)
- [👾 Other Playgrounds](#-other-playgrounds)
- [📚 Useful Resources](#-useful-resources)

## 🔗 Kafka Connectors

Quick start examples from Confluent [docs](https://docs.confluent.io/current/connect/managing/index.html) but in Docker version for ease of use.

| Connector  | Product Category  | Latest Version (*) | Type | Release Date| CP 6.1.1 [CI](https://github.com/vdesabou/kafka-docker-playground/actions?query=workflow%3ACI) latest results| CP 6.0.2 [CI](https://github.com/vdesabou/kafka-docker-playground/actions?query=workflow%3ACI) latest results| CP 5.5.3 [CI](https://github.com/vdesabou/kafka-docker-playground/actions?query=workflow%3ACI) latest results
|---|---|---|---|---|---|---|---|
| <img src="./images/icons/activemq.png" width="15"> [ActiveMQ Sink](connect/connect-active-mq-sink)  | Message Queue  | 1.3.2 | Confluent Subscription | 2021-02-19 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/activemq.png" width="15"> [ActiveMQ Source](connect/connect-active-mq-source)  | Message Queue  | 11.0.2 | Confluent Subscription | 2021-03-17 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/cloudwatch_logs.svg" width="15"> [Amazon CloudWatch Logs Source](connect/connect-aws-cloudwatch-logs-source)  | Analytics  | 1.1.0 | Confluent Subscription | 2021-01-06 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203685) [🐞 #855](https://github.com/vdesabou/kafka-docker-playground/issues/855) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202846) [🐞 #855](https://github.com/vdesabou/kafka-docker-playground/issues/855) | [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368281368) | 
| <img src="./images/icons/cloudwatch_logs.svg" width="15"> [Amazon CloudWatch Metrics Sink](connect/connect-aws-cloudwatch-metrics-sink)  | Analytics  | 1.1.4 | Confluent Subscription | 2021-03-25 |  [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368282050) | [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368281836) | [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368281368) | 
| <img src="./images/icons/dynamodb.svg" width="15"> [Amazon DynamoDB Sink](connect/connect-aws-dynamodb-sink) | Database  | 1.1.4 | Confluent Subscription | 2020-12-01 |  [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368282050) | [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368281836) | [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368281368) | 
| <img src="./images/icons/kinesis.svg" width="15"> [Amazon Kinesis Source](connect/connect-aws-kinesis-source) (also with 🌐 proxy) | Message Queue  | 1.3.5 | Confluent Subscription | 2021-04-13 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203685) [🐞 #869](https://github.com/vdesabou/kafka-docker-playground/issues/869) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202846) [🐞 #869](https://github.com/vdesabou/kafka-docker-playground/issues/869) | [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368281368) | 
| <img src="./images/icons/aws_redshift.png" width="15"> [Amazon Redshift Sink](connect/connect-aws-redshift-sink) | Data Warehouse  | 1.0.5 | Confluent Subscription | 2021-02-22 |  🤷‍♂️ not tested | 🤷‍♂️ not tested | 🤷‍♂️ not tested | 
| <img src="./images/icons/aws_redshift.png" width="15"> [Amazon Redshift Source](connect/connect-jdbc-aws-redshift-source) (using JDBC) | Data Warehouse  | :connect/connect-jdbc-aws-redshift-source:
| <img src="./images/icons/s3.png" width="15"> [Amazon S3 Sink](connect/connect-aws-s3-sink) | Datastore  | 10.0.0 | Confluent Community License | 2021-03-03 |  [👍 2021-04-18](https://github.com/vdesabou/kafka-docker-playground/runs/2373258055) | [👍 2021-04-18](https://github.com/vdesabou/kafka-docker-playground/runs/2373257699) | [👍 2021-04-18](https://github.com/vdesabou/kafka-docker-playground/runs/2373257371) | 
| <img src="./images/icons/s3.png" width="15"> [Amazon S3 Source](connect/connect-aws-s3-source)  | Datastore  | 1.4.5 | Confluent Subscription | 2021-04-08 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203715) [🐞 #870](https://github.com/vdesabou/kafka-docker-playground/issues/870) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202881) [🐞 #870](https://github.com/vdesabou/kafka-docker-playground/issues/870) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202244) [🐞 #870](https://github.com/vdesabou/kafka-docker-playground/issues/870) | 
| <img src="./images/icons/sqs.svg" width="15"> [Amazon SQS Source](connect/connect-aws-sqs-source)  | Message Queue  | 1.1.1 | Confluent Subscription | 2021-01-30 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203715) [🐞 #863](https://github.com/vdesabou/kafka-docker-playground/issues/863) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202881) [🐞 #863](https://github.com/vdesabou/kafka-docker-playground/issues/863) | [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368281374) | 
| <img src="./images/icons/amps.png" width="15"> [AMPS Source](connect/connect-amps-source)  | Message Queue  | 1.0.0-preview | Confluent Subscription | 2020-07-08 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/kudu.png" width="15"> [Apache Kudu Source](connect/connect-kudu-source)  | Database  | 1.0.2 | Confluent Subscription | 2021-03-12 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](https://github.com/vdesabou/kafka-docker-playground/runs/2366522047) | 
| <img src="./images/icons/kudu.png" width="15"> [Apache Kudu Sink](connect/connect-kudu-sink)  | Database  | 1.0.2 | Confluent Subscription | 2021-03-12 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/lambda.svg" width="15"> [AWS Lambda Sink](connect/connect-aws-lambda-sink)  | SaaS Apps  | 1.1.1 | Confluent Subscription | 2021-01-07 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203685) [🐞 #856](https://github.com/vdesabou/kafka-docker-playground/issues/856) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202846) [🐞 #856](https://github.com/vdesabou/kafka-docker-playground/issues/856) | [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368281368) | 
| <img src="./images/icons/blob_storage.png" width="15"> [Azure Blob Storage Sink](connect/connect-azure-blob-storage-sink)  | Datastore | 1.6.2 | Confluent Subscription | 2021-04-12 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/blob_storage.png" width="15"> [Azure Blob Storage Source](connect/connect-azure-blob-storage-source)  | Datastore | 1.4.5 | Confluent Subscription | 2021-04-08 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203763) [🐞 #778](https://github.com/vdesabou/kafka-docker-playground/issues/778) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202950) [🐞 #778](https://github.com/vdesabou/kafka-docker-playground/issues/778) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202271) [🐞 #778](https://github.com/vdesabou/kafka-docker-playground/issues/778) | 
| <img src="./images/icons/cosmosdb.png" width="15"> [Azure Cosmos DB Sink](connect/connect-azure-cosmosdb-sink)  | Datastore | 1.0.4-beta | MIT License | 2021-02-24 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/cosmosdb.png" width="15"> [Azure Cosmos DB Source](connect/connect-azure-cosmosdb-source)  | Datastore | 1.0.4-beta | MIT License | 2021-02-24 |  [👍 2021-04-16](null) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203460) [🐞 #846](https://github.com/vdesabou/kafka-docker-playground/issues/846) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202502) [🐞 #846](https://github.com/vdesabou/kafka-docker-playground/issues/846) | 
| <img src="./images/icons/data_lake_gen1.png" width="15"> [Azure Data Lake Storage Gen1 Sink](connect/connect-azure-data-lake-storage-gen1-sink)  | Datastore | 1.6.2 | Confluent Subscription | 2021-04-12 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/data_lake_gen1.png" width="15"> [Azure Data Lake Storage Gen2 Sink](connect/connect-azure-data-lake-storage-gen2-sink)  | Datastore | 1.6.2 | Confluent Subscription | 2021-04-12 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/event_hubs.png" width="15"> [Azure Event Hubs Source](connect/connect-azure-event-hubs-source)  | Message Queue | 1.2.0 | Confluent Subscription | 2021-02-19 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/azure_functions.png" width="15"> [Azure Functions Sink](connect/connect-azure-functions-sink) | SaaS Apps | 1.0.9 | Confluent Subscription | 2021-02-09 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203763) [🐞 #876](https://github.com/vdesabou/kafka-docker-playground/issues/876) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202950) [🐞 #876](https://github.com/vdesabou/kafka-docker-playground/issues/876) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202271) [🐞 #876](https://github.com/vdesabou/kafka-docker-playground/issues/876) | 
| <img src="./images/icons/search.png" width="15"> [Azure Search Sink](connect/connect-azure-search-sink)  | Analytics | 1.0.4 | Confluent Subscription | 2021-02-03 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/service_bus.png" width="15"> [Azure Service Bus Source](connect/connect-azure-service-bus-source)  | Message Queue | 1.1.3 | Confluent Subscription | 2021-01-29 |  [👍 2021-04-16](https://github.com/vdesabou/kafka-docker-playground/runs/2366146626) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/sql_data_warehouse.png" width="15"> [Azure SQL Data Warehouse Sink](connect/connect-azure-sql-data-warehouse-sink)  | Data Warehouse | 1.0.4 | Confluent Subscription | 2020-10-08 |  [👍 2021-04-16](https://github.com/vdesabou/kafka-docker-playground/runs/2366523203) | [👍 2021-04-16](https://github.com/vdesabou/kafka-docker-playground/runs/2366146166) | [👍 2021-04-16](https://github.com/vdesabou/kafka-docker-playground/runs/2366145598) | 
| <img src="./images/icons/cassandra.png" width="15"> [Cassandra Sink](connect/connect-cassandra-sink)  | Database | 2.0.0 | Confluent Subscription | 2020-12-04 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/couchbase.svg" width="15"> [Couchbase Sink](connect/connect-couchbase-sink)  | Database | 4.0.5 | Open Source (Couchbase, Inc.) | 2021-03-15 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/couchbase.svg" width="15"> [Couchbase Source](connect/connect-couchbase-source)  | Database | 4.0.5 | Open Source (Couchbase, Inc.) | 2021-03-15 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203507) [🐞 #837](https://github.com/vdesabou/kafka-docker-playground/issues/837) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202568) [🐞 #837](https://github.com/vdesabou/kafka-docker-playground/issues/837) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202107) [🐞 #837](https://github.com/vdesabou/kafka-docker-playground/issues/837) | 
| <img src="./images/icons/sql_server.png" width="15"> [Debezium CDC Microsoft SQL Server Source](connect/connect-debezium-sqlserver-source)  | CDC | 1.5.0 | Open Source (Debezium Community) |  |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/mysql.jpg" width="15"> [Debezium CDC MySQL Source](connect/connect-debezium-mysql-source)  | CDC | 1.5.0 | Open Source (Debezium Community) |  |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/postgresql.png" width="15"> [Debezium CDC PostgreSQL Source](connect/connect-debezium-postgresql-source)  | CDC | 1.4.1 | Open Source (Debezium Community) |  |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/mongodb.jpg" width="15"> [Debezium CDC MongoDB Source](connect/connect-debezium-mongodb-source)  | CDC | 1.5.0 | Open Source (Debezium Community) |  |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/data_diode.jpg" width="15"> [Data Diode Sink](connect/connect-datadiode-source-sink) | Logs | 1.1.1 | Confluent Subscription | 2019-10-18 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/data_diode.jpg" width="15"> [Data Diode Source](connect/connect-datadiode-source-sink) | Logs | 1.1.1 | Confluent Subscription | 2019-10-18 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/datadog.png" height="15"> [Datadog Metrics Sink](connect/connect-datadog-metrics-sink) | Analytics | 1.1.4 | Confluent Subscription | 2021-03-25 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/elasticsearch.png" width="15"> [ElasticSearch Sink](connect/connect-elasticsearch-sink) | Analytics | 11.0.3 | Confluent Community License | 2021-03-12 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/ftps.png" height="15"> [FTPS Sink](connect/connect-ftps-sink) | Datastore |1.0.3-preview | Confluent Subscription | 2020-10-01 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/ftps.png" height="15"> [FTPS Source](connect/connect-ftps-source) | Datastore |1.0.3-preview | Confluent Subscription | 2020-10-01 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/pivotal_gemfire.png" width="15"> [Gemfire Sink](connect/connect-pivotal-gemfire-sink) | Database | 1.0.6 | Confluent Subscription | 2021-03-09 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/github.png" width="15"> [Github Source](connect/connect-github-source) | SaaS Apps | 1.0.4 | Confluent Subscription | 2021-03-09 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/bigquery.png" width="15"> [Google BigQuery Sink](connect/connect-gcp-bigquery-sink) | Data Warehouse | 2.1.3 | Open Source (WePay) | 2021-04-09 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/gcp_bigtable.png" width="15"> [Google Cloud BigTable Sink](connect/connect-gcp-bigtable-sink) | Database | 1.0.7 | Confluent Subscription | 2021-03-05 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/cloud_functions.png" width="15"> [Google Cloud Functions Sink](connect/connect-gcp-cloud-functions-sink) | SaaS Apps | 1.1.3 | Confluent Subscription | 2021-02-09 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/gcp_pubsub.png" width="15"> [Google Cloud Pub/Sub Source](connect/connect-gcp-pubsub-source) (also with 🌐 proxy) |  Message Queue | 1.0.6 | Confluent Subscription | 2021-01-16 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/spanner.png" width="15"> [Google Cloud Spanner Sink](connect/connect-gcp-spanner-sink) |  Database | 1.0.5 | Confluent Subscription | 2021-03-11 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203890) [🐞 #792](https://github.com/vdesabou/kafka-docker-playground/issues/792) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203275) [🐞 #792](https://github.com/vdesabou/kafka-docker-playground/issues/792) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202352) [🐞 #792](https://github.com/vdesabou/kafka-docker-playground/issues/792) | 
| <img src="./images/icons/gcs.png" width="15"> [Google Cloud Storage Sink](connect/connect-gcp-gcs-sink) |  Datastore | 5.5.5 | Confluent Subscription | 2020-12-29 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/gcs.png" width="15"> [Google Cloud Storage Source](connect/connect-gcp-gcs-source) |  Datastore | 1.4.5 | Confluent Subscription | 2021-04-08 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/firebase.svg" width="15"> [Google Firebase Realtime Database Sink](connect/connect-gcp-firebase-sink) |  Database | 1.2.0 | Confluent Subscription | 2020-12-01 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/firebase.svg" width="15"> [Google Firebase Realtime Database Source](connect/connect-gcp-firebase-source) |  Database | 1.2.0 | Confluent Subscription | 2020-12-01 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/hbase.png" width="15"> [HBase Sink](connect/connect-hbase-sink) |  Database | 1.0.7 | Confluent Subscription | 2021-03-05 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203507) [🐞 #878](https://github.com/vdesabou/kafka-docker-playground/issues/878) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202568) [🐞 #878](https://github.com/vdesabou/kafka-docker-playground/issues/878) | [👍 2021-04-18](https://github.com/vdesabou/kafka-docker-playground/runs/2373257267) | 
| <img src="./images/icons/hdfs_2.svg" width="15"> [HDFS 2 Source](connect/connect-hdfs2-source) |  Datastore | 1.4.5 | Confluent Subscription | 2021-04-08 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/hdfs_2.svg" width="15"> [HDFS 3 Source](connect/connect-hdfs3-source) |  Datastore | 1.4.5 | Confluent Subscription | 2021-04-08 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/hdfs_2.svg" width="15"> [HDFS 2 Sink](connect/connect-hdfs2-sink) |  Datastore | 10.0.2 | Confluent Community License | 2021-03-15 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/hdfs_2.svg" width="15"> [HDFS 3 Sink](connect/connect-hdfs3-sink) |  Datastore | 1.1.1 | Confluent Subscription | 2021-03-08 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/http.png" width="15"> [HTTP Sink](connect/connect-http-sink) |  SaaS Apps | 1.3.0 | Confluent Subscription | 2021-04-02 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/ibm_mq.png" width="15"> [IBM MQ Sink](connect/connect-ibm-mq-sink) |  Message Queue | 1.3.2 | Confluent Subscription | 2021-02-19 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/ibm_mq.png" width="15"> [IBM MQ Source](connect/connect-ibm-mq-source) |  Message Queue | 11.0.2 | Confluent Subscription | 2021-03-17 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/influxdb.svg" width="15"> [InfluxDB Sink](connect/connect-influxdb-sink) |  Database | 1.2.1 | Confluent Subscription | 2020-09-30 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/influxdb.svg" width="15"> [InfluxDB Source](connect/connect-influxdb-source) |  Database | 1.2.1 | Confluent Subscription | 2020-09-30 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/hive.png" width="15"> [JDBC Hive Sink](connect/connect-jdbc-hive-sink) |  Database | :connect/connect-jdbc-hive-sink:
| <img src="./images/icons/mysql.jpg" width="15"> [JDBC MySQL Sink](connect/connect-jdbc-mysql-sink) (also with 🔑 SSL and mTLS) |  Database | 10.1.1 | Confluent Community License | 2021-04-13 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203542) [🐞 #879](https://github.com/vdesabou/kafka-docker-playground/issues/879) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202660) [🐞 #879](https://github.com/vdesabou/kafka-docker-playground/issues/879) | [👍 2021-04-16](https://github.com/vdesabou/kafka-docker-playground/runs/2366145439) | 
| <img src="./images/icons/oracle_11.jpg" width="15"> [JDBC Oracle 11 Sink](connect/connect-jdbc-oracle11-sink) |  Database | 10.1.1 | Confluent Community License | 2021-04-13 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/oracle_12.jpg" width="15"> [JDBC Oracle 12 Sink](connect/connect-jdbc-oracle12-sink) (also with 🔑 SSL and mTLS) |  Database | 10.1.1 | Confluent Community License | 2021-04-13 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203624) [🐞 #881](https://github.com/vdesabou/kafka-docker-playground/issues/881) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202775) [🐞 #881](https://github.com/vdesabou/kafka-docker-playground/issues/881) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202200) [🐞 #881](https://github.com/vdesabou/kafka-docker-playground/issues/881) | 
| <img src="./images/icons/postgresql.png" width="15"> [JDBC PostGreSQL Sink](connect/connect-jdbc-postgresql-sink) |  Database | 10.1.1 | Confluent Community License | 2021-04-13 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/sql_server.png" width="15"> [JDBC Microsoft SQL Server Sink](connect/connect-jdbc-sqlserver-sink) |  Database | 10.1.1 | Confluent Community License | 2021-04-13 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/vertica.png" width="15"> [JDBC Vertica Sink](connect/connect-jdbc-vertica-sink) |  Database | 10.1.1 | Confluent Community License | 2021-04-13 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/mysql.jpg" width="15"> [JDBC MySQL Source](connect/connect-jdbc-mysql-source) (also with 🔑 SSL and mTLS) |  Database | 10.1.1 | Confluent Community License | 2021-04-13 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203542) [🐞 #880](https://github.com/vdesabou/kafka-docker-playground/issues/880) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202660) [🐞 #880](https://github.com/vdesabou/kafka-docker-playground/issues/880) | [👍 2021-04-16](null) | 
| <img src="./images/icons/oracle_11.jpg" width="15"> [JDBC Oracle 11 Source](connect/connect-jdbc-oracle11-source) |  Database | 10.1.1 | Confluent Community License | 2021-04-13 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/oracle_12.jpg" width="15"> [JDBC Oracle 12 Source](connect/connect-jdbc-oracle12-source) (also with 🔑 SSL and mTLS) |  Database | 10.1.1 | Confluent Community License | 2021-04-13 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203624) [🐞 #882](https://github.com/vdesabou/kafka-docker-playground/issues/882) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202775) [🐞 #882](https://github.com/vdesabou/kafka-docker-playground/issues/882) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202200) [🐞 #882](https://github.com/vdesabou/kafka-docker-playground/issues/882) | 
| <img src="./images/icons/postgresql.png" width="15"> [JDBC PostGreSQL Source](connect/connect-jdbc-postgresql-source) |  Database | 10.1.1 | Confluent Community License | 2021-04-13 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203542) [🐞 #851](https://github.com/vdesabou/kafka-docker-playground/issues/851) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202660) [🐞 #851](https://github.com/vdesabou/kafka-docker-playground/issues/851) | [👍 2021-04-16](null) | 
| <img src="./images/icons/sql_server.png" width="15"> [JDBC Microsoft SQL Server Source](connect/connect-jdbc-sqlserver-source) |  Database | 10.1.1 | Confluent Community License | 2021-04-13 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/jira.png" width="15"> [JIRA Source](connect/connect-jira-source) |  SaaS Apps | 1.0.4-preview | Confluent Subscription | 2021-03-22 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/activemq.png" width="15"> [JMS ActiveMQ Sink](connect/connect-jms-active-mq-sink) |  Message Queue | 1.3.2 | Confluent Subscription | 2021-02-19 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/solace.jpg" width="15"> [JMS Solace Sink](connect/connect-jms-solace-sink) |  Message Queue | 1.3.2 | Confluent Subscription | 2021-02-19 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/tibco_ems.png" width="15"> [JMS TIBCO EMS Sink](connect/connect-jms-tibco-sink) |  Message Queue | 1.3.2 | Confluent Subscription | 2021-02-19 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/tibco_ems.png" width="15"> [JMS TIBCO EMS Source](connect/connect-jms-tibco-source) |  Message Queue | 11.0.2 | Confluent Subscription | 2021-03-17 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/weblogic.png" width="15"> [JMS Oracle Weblogic Source](connect/connect-jms-weblogic-source) |  Message Queue | 11.0.2 | Confluent Subscription | 2021-03-17 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/mapr.png" height="15"> [Mapr Sink](connect/connect-mapr-sink) |  Datastore | 1.1.3 | Confluent Subscription | 2021-03-11 |  🤷‍♂️ not tested | 🤷‍♂️ not tested | 🤷‍♂️ not tested | 
| <img src="./images/icons/marketo.png" height="15"> [Marketo Source](connect/connect-marketo-source) |  SaaS Apps | 1.0.0-preview | Confluent Subscription | 2020-10-20 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/minio.png" height="15"> [Minio Sink](connect/connect-minio-s3-sink) |  Datastore | 10.0.0 | Confluent Community License | 2021-03-03 |  [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368281962) | [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368281591) | [👍 2021-04-17](https://github.com/vdesabou/kafka-docker-playground/runs/2368281310) | 
| <img src="./images/icons/mongodb.jpg" width="15"> [MongoDB Sink](connect/connect-mongodb-sink) |  Database | 1.2.0 | Open Source (MongoDB) | 2020-07-08 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/mongodb.jpg" width="15"> [MongoDB Source](connect/connect-mongodb-source) |  Database | 1.2.0 | Open Source (MongoDB) | 2020-07-08 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/mqtt.png" width="15"> [MQTT Sink](connect/connect-mqtt-sink) |  IoT | 1.4.0 | Confluent Subscription | 2020-10-29 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/mqtt.png" width="15"> [MQTT Source](connect/connect-mqtt-source) |  IoT | 1.4.0 | Confluent Subscription | 2020-10-29 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/neo4j.png" width="15"> [Neo4j Sink](connect/connect-neo4j-sink) |  Database | 1.0.9 | Open Source (Neo4j, Inc.) | 2020-09-02 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/omnisci.png" width="15"> [OmniSci Sink](connect/connect-omnisci-sink) |  Database | 1.0.2 | Confluent Subscription | 2019-08-20 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/oracle_12.jpg" width="15"> [Oracle CDC](connect/connect-cdc-oracle12-source) (also with 🔑 SSL and mTLS) |  Database | 1.0.5 | Confluent Subscription | 2021-03-09 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203970) [🐞 #829](https://github.com/vdesabou/kafka-docker-playground/issues/829) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203422) [🐞 #829](https://github.com/vdesabou/kafka-docker-playground/issues/829) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202468) [🐞 #829](https://github.com/vdesabou/kafka-docker-playground/issues/829) | 
| <img src="./images/icons/pagerduty.png" width="15"> [PagerDuty Sink](connect/connect-pagerduty-sink) |  SaaS Apps | 1.0.2 | Confluent Subscription | 2020-11-18 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/prometheus.png" height="15">  [Prometheus Sink](connect/connect-prometheus-sink) |  Analytics | 1.1.4-preview | Confluent Subscription | 2021-03-25 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/rabbitmq.svg" width="15"> [RabbitMQ Sink](connect/connect-rabbitmq-sink) |  Message Queue | 1.5.0 | Confluent Subscription | 2021-03-04 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/rabbitmq.svg" width="15">  [RabbitMQ Source](connect/connect-rabbitmq-source) |  Message Queue | 1.5.0 | Confluent Subscription | 2021-03-04 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/redis.jpg" width="15"> [Redis Sink](connect/connect-redis-sink) |  Database | 0.0.2.12 | Open Source (Jeremy Custenborder) | 2021-03-24 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/salesforce.png" height="15"> [SalesForce Bulk API Sink](connect/connect-salesforce-bulkapi-sink) |  SaaS Apps | 1.8.2 | Confluent Subscription | 2021-04-14 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/salesforce.png" height="15"> [SalesForce Bulk API Source](connect/connect-salesforce-bulkapi-source) |  SaaS Apps | 1.8.2 | Confluent Subscription | 2021-04-14 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/salesforce.png" height="15"> [SalesForce CDC Source](connect/connect-salesforce-cdc-source) |  SaaS Apps | 1.8.2 | Confluent Subscription | 2021-04-14 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/salesforce.png" height="15"> [SalesForce Platform Events Sink](connect/connect-salesforce-platform-events-sink) |  SaaS Apps | 1.8.2 | Confluent Subscription | 2021-04-14 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/salesforce.png" height="15"> [SalesForce Platform Events Source](connect/connect-salesforce-platform-events-source) |  SaaS Apps | 1.8.2 | Confluent Subscription | 2021-04-14 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/salesforce.png" height="15"> [SalesForce PushTopics Source](connect/connect-salesforce-pushtopics-source) |  SaaS Apps | 1.8.2 | Confluent Subscription | 2021-04-14 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/salesforce.png" height="15"> [SalesForce SObject Sink](connect/connect-salesforce-sobject-sink) |  SaaS Apps | 1.8.2 | Confluent Subscription | 2021-04-14 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/servicenow.png" width="15"> [ServiceNow Sink](connect/connect-servicenow-sink) |  SaaS Apps | 2.1.1 | Confluent Subscription | 2021-04-12 |  🤷‍♂️ not tested | 🤷‍♂️ not tested | 🤷‍♂️ not tested | 
| <img src="./images/icons/servicenow.png" width="15"> [ServiceNow Source](connect/connect-servicenow-source) (also with 🌐 proxy) |  SaaS Apps | 2.1.1 | Confluent Subscription | 2021-04-12 |  🤷‍♂️ not tested | 🤷‍♂️ not tested | 🤷‍♂️ not tested | 
| <img src="./images/icons/sftp.png" width="15"> [SFTP Sink](connect/connect-sftp-sink) |  Datastore | 2.2.4 | Confluent Subscription | 2021-02-23 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/sftp.png" width="15"> [SFTP Source](connect/connect-sftp-source) |  Datastore | 2.2.4 | Confluent Subscription | 2021-02-23 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/snmp_trap.png" width="15"> [SNMP Trap Source](connect/connect-snmp-source) |  IoT | 1.1.2 | Confluent Subscription | 2020-04-09 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/snowflake.png" height="15">  [Snowflake Sink](connect/connect-snowflake-sink) |  Data Warehouse | 1.5.2 | Open Source (Snowflake, Inc.) | 2021-02-01 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/solace.jpg" width="15"> [Solace Sink](connect/connect-solace-sink) |  Message Queue | 1.3.2 | Confluent Subscription | 2021-02-19 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/solace.jpg" width="15"> [Solace Source](connect/connect-solace-source) |  Message Queue | 1.2.0 | Confluent Subscription | 2020-08-26 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/splunk.jpg" width="15"> [Splunk Sink](connect/connect-splunk-sink) |  Analytics | 2.0.2 | Open Source (Splunk) |  |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/splunk.jpg" width="15"> [Splunk Source](connect/connect-splunk-source) |  Analytics | 1.0.3 | Confluent Subscription | 2020-11-18 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/spool_dir.png" width="15"> [Spool Dir Source](connect/connect-spool-dir-source) |  Datastore | 2.0.61 | Open Source (Jeremy Custenborder) | 2021-03-26 |  [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387203497) [🐞 #862](https://github.com/vdesabou/kafka-docker-playground/issues/862) | [❌ 2021-04-20](https://github.com/vdesabou/kafka-docker-playground/runs/2387202548) [🐞 #862](https://github.com/vdesabou/kafka-docker-playground/issues/862) | [👍 2021-04-16](null) | 
| <img src="./images/icons/syslog.png" width="15"> [Syslog Source](connect/connect-syslog-source) |  Logs | 1.3.2 | Confluent Subscription | 2020-11-03 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/tibco_ems.png" width="15"> [TIBCO EMS Sink](connect/connect-tibco-sink) |  Message Queue | 1.3.2 | Confluent Subscription | 2021-02-19 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/tibco_ems.png" width="15"> [TIBCO EMS Source](connect/connect-tibco-source) |  Message Queue | 1.2.0 | Confluent Subscription | 2020-08-26 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/vertica.png" width="15"> [Vertica Sink](connect/connect-vertica-sink) |  Database | 1.2.5 | Confluent Subscription | 2021-02-18 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 
| <img src="./images/icons/zendesk.png" width="15"> [Zendesk Source](connect/connect-zendesk-source) |  SaaS Apps | 1.0.6 | Confluent Subscription | 2021-03-09 |  [👍 2021-04-16](null) | [👍 2021-04-16](null) | [👍 2021-04-16](null) | 

\* You can change default connector version by setting `CONNECTOR_TAG` environment variable before starting a test, get more details [here](https://github.com/vdesabou/kafka-docker-playground/wiki/How-to-run#default-connector-version)

## ☁️ Confluent Cloud

### [Confluent Cloud Demo](ccloud/ccloud-demo)

  - How to connect your components to Confluent Cloud
  - How to monitor your Confluent Cloud cluster
  - How to restrict access
  - etc...

![Diagram](./ccloud/ccloud-demo/images/diagram.png)

### 🔗 Kafka Connectors connected to Confluent Cloud

  - <img src="./images/icons/kinesis.svg" width="15"> [AWS Kinesis](ccloud/connect-aws-kinesis-source) source
  - <img src="./images/icons/servicenow.png" width="15"> [ServiceNow](ccloud/connect-servicenow-source) source
  - <img src="./images/icons/servicenow.png" width="15"> [ServiceNow](ccloud/connect-servicenow-sink) sink
  - <img src="./images/icons/mongodb.jpg" width="15"> [MongoDB](ccloud/connect-debezium-mongodb-source) source
  - <img src="./images/icons/firebase.svg" width="15"> [Firebase](ccloud/connect-gcp-firebase-sink)

### Other

  - Using [cp-ansible](ccloud/cp-ansible-playground/) with Confluent Cloud
  - Using [cp-helm-charts](ccloud/cp-helm-chart/) with Confluent Cloud
  - Using [confluent operator](ccloud/operator/) with Confluent Cloud
  - Demo using [dabz/ccloudexporter](https://github.com/Dabz/ccloudexporter) in order to pull [Metrics API](https://docs.confluent.io/current/cloud/metrics-api.html) data from Confluent Cloud cluster and export it to Prometheus (Grafana dashboard is also available)
  - <img src="https://www.pngitem.com/pimgs/m/33-335825_-net-core-logo-png-transparent-png.png" width="15"> [.NET](ccloud/client-dotnet) client (producer/consumer)
  - <img src="https://github.com/confluentinc/examples/raw/5.4.1-post/clients/cloud/images/go.png" width="15"> [Go](ccloud/client-go) client (producer/consumer)
  - <img src="https://vectorified.com/images/admin-icon-png-14.png" width="15"> [kafka-admin](ccloud/kafka-admin) Managing topics and ACLs using [matt-mangia/kafka-admin](https://github.com/matt-mangia/kafka-admin)
  - <img src="https://img.icons8.com/cotton/2x/synchronize--v1.png" width="15"> Confluent Replicator [OnPrem to cloud and Cloud to Cloud examples](ccloud/replicator)
  - <img src="https://avatars3.githubusercontent.com/u/9439498?s=60&v=4" width="15"> [Multi-Cluster Schema Registry](ccloud/multiple-sr-hybrid) with hybrid configuration (onprem/confluent cloud)
  - [Confluent REST Proxy Security Plugin](ccloud/rest-proxy-security-plugin) with Principal Propagation
  - [Confluent Schema Registry Security Plugin](ccloud/schema-registry-security-plugin)
  - [Migrate Schemas to Confluent Cloud](ccloud/migrate-schemas-to-confluent-cloud) using Confluent Replicator
  - [Confluent Cloud Networking](ccloud/haproxy) using HAProxy

## 🔄 Confluent Replicator and Mirror Maker 2

Using Multi-Data-Center setup with `US` 🇺🇸 and `EUROPE` 🇪🇺 clusters.

- <img src="./images/icons/using_confluent_replicator_as_connector.png" width="15"> [Using Confluent Replicator as connector](replicator/connect)
  - Using [PLAINTEXT](environment/mdc-plaintext)
  - Using [SASL_PLAIN](environment/mdc-sasl-plain)
  - Using [Kerberos](environment/mdc-kerberos)
- 👾 [Using Confluent Replicator as executable](replicator/executable)
  - Using [PLAINTEXT](environment/mdc-plaintext)
  - Using [SASL_PLAIN](environment/mdc-sasl-plain)
  - Using [Kerberos](environment/mdc-kerberos)
- <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/05/Apache_kafka.svg/1200px-Apache_kafka.svg.png" width="16"> [Using Mirror Maker 2](replicator/mirrormaker2)
  - Using [PLAINTEXT](environment/mdc-plaintext)

## 🔐 Environments

Single cluster:

- [PLAINTEXT](environment/plaintext): no security
- [SASL_PLAIN](environment/sasl-plain): no SSL encryption, SASL/PLAIN authentication
- [SASL/SCRAM](environment/sasl-scram) no SSL encryption, SASL/SCRAM-SHA-256 authentication
- [SASL_SSL](environment/sasl-ssl): SSL encryption, SASL/PLAIN authentication
- [2WAY_SSL](environment/2way-ssl): SSL encryption, SSL authentication
- [Kerberos](environment/kerberos): no SSL encryption, Kerberos GSSAPI authentication
- [SSL_Kerberos](environment/ssl_kerberos) SSL encryption, Kerberos GSSAPI authentication
- [LDAP Authorizer with SASL/PLAIN](environment/ldap_authorizer_sasl_plain) no SSL encryption, SASL/PLAIN authentication, LDAP Authorizer for ACL authorization
- [RBAC with SASL/PLAIN](environment/rbac-sasl-plain) RBAC with no SSL encryption, SASL/PLAIN authentication

Multi-Data-Center setup:

- [PLAINTEXT](environment/mdc-plaintext): no security
- [SASL_PLAIN](environment/mdc-sasl-plain): no SSL encryption, SASL/PLAIN authentication
- [Kerberos](environment/mdc-kerberos): no SSL encryption, Kerberos GSSAPI authentication


## Confluent Commercial

- Control Center
  - [Control Center in "Read-Only" mode](other/control-center-readonly-mode/)
  - [Configuring Control Center with LDAP authentication](other/control-center-ldap-auth)
- Tiered Storage
  - [Tiered storage with AWS S3](other/tiered-storage-with-aws)
  - [Tiered storage with Minio](other/tiered-storage-with-minio) (unsupported)
- [Confluent Rebalancer](other/rebalancer)
- [JMS Client](other/jms-client)
- [RBAC with SASL/PLAIN](environment/rbac-sasl-plain) RBAC with no SSL encryption, SASL/PLAIN authentication
- [Audit Logs](other/audit-logs)
- [Confluent REST Proxy Security Plugin](other/rest-proxy-security-plugin) with SASL_SSL and 2WAY_SSL Principal Propagation

## [CP-Ansible Playground](other/cp-ansible-playground)

Easily play with Confluent Platform Ansible playbooks by using Ubuntu based Docker images generated daily from this [cp-ansible-playground](https://github.com/vdesabou/cp-ansible-playground) repository

There is also a Confluent Cloud version available [here](ccloud/cp-ansible-playground/)

## 👾 Other Playgrounds

- [Confluent Replicator](connect/connect-replicator) [also with [SASL_SSL](connect/connect-replicator/README.md#with-sasl-ssl-authentication) and [2WAY_SSL](connect/connect-replicator/README.md#with-ssl-authentication)]
- Testing [Separate principals](https://docs.confluent.io/current/connect/security.html#separate-principals) (`connector.client.config.override.policy`) for [Source connector (SFTP source)](other/connect-override-policy-sftp-source)
- Testing [Separate principals](https://docs.confluent.io/current/connect/security.html#separate-principals) (`connector.client.config.override.policy`) for [Source connector (SFTP sink)](other/connect-override-policy-sftp-sink)
- [How to write logs to files when using docker-compose](other/write-logs-to-files)
- [Publish logs to kafka with Elastic Filebeat](other/filebeat-to-kafka)
- <img src="https://www.pngitem.com/pimgs/m/33-335825_-net-core-logo-png-transparent-png.png" width="15"> [.NET](other/client-dotnet) basic producer
- <img src="https://datadog-docs.imgix.net/images/dd-docs-meta-image.png" width="15"> [Monitor Confluent Platform with Datadog](tools/datadog)

## 📚 Useful Resources

- [A Kafka Story 📖](https://github.com/framiere/a-kafka-story): A step by step guide to use Kafka ecosystem (Kafka Connect, KSQL, Java Consumers/Producers, etc..) with Docker
- [Kafka Boom Boom 💥](https://github.com/Dabz/kafka-boom-boom): An attempt to break kafka
- [Kafka Security playbook 🔒](https://github.com/Dabz/kafka-security-playbook): demonstrates various security configurations with Docker
- [MDC and single views 🌍](https://github.com/framiere/mdc-with-replicator-and-regexrouter): Multi-Data-Center setup using Confluent [Replicator](https://docs.confluent.io/current/connect/kafka-connect-replicator/index.html)
- [Kafka Platform Prometheus 📊](https://github.com/jeanlouisboudart/kafka-platform-prometheus): Simple demo of how to monitor Kafka Platform using Prometheus and Grafana.
