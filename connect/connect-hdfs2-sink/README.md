# HDFS 2 Sink connector

![asciinema](https://github.com/vdesabou/gifs/blob/master/connect/connect-hdfs2-sink/asciinema.gif?raw=true)

## Objective

Quickly test [HDFS 2 Sink](https://docs.confluent.io/current/connect/kafka-connect-hdfs/index.html) connector.



## How to run

Simply run:

```
$ ./hdfs2.sh
```

## Details of what the script is doing

The connector is created with:

```
curl -X PUT \
     -H "Content-Type: application/json" \
     --data '{
        "connector.class":"io.confluent.connect.hdfs.HdfsSinkConnector",
               "tasks.max":"1",
               "topics":"test_hdfs",
               "hdfs.url":"hdfs://hadoop:9000",
               "flush.size":"3",
               "hadoop.conf.dir":"/usr/local/hadoop-2.7.1/etc/hadoop/",
               "partitioner.class":"io.confluent.connect.hdfs.partitioner.FieldPartitioner",
               "partition.field.name":"f1",
               "rotate.interval.ms":"120000",
               "hadoop.home":"/usr/local/hadoop-2.7.1/share/hadoop/common/",
               "logs.dir":"/tmp",
               "schema.compatibility":"BACKWARD"
          }' \
     http://localhost:8083/connectors/hdfs-sink/config | jq .
```

Messages are sent to `test_hdfs` topic using:

```
$ seq -f "{\"f1\": \"value%g\"}" 10 | docker exec -i connect kafka-avro-console-producer --broker-list broker:9092 --property schema.registry.url=http://schema-registry:8081 --topic test_hdfs --property value.schema='{"type":"record","name":"myrecord","fields":[{"name":"f1","type":"string"}]}'
```

After a few seconds, HDFS should contain files in /topics/test_hdfs:

```
$ docker exec hadoop bash -c "/usr/local/hadoop/bin/hdfs dfs -ls /topics/test_hdfs"

drwxr-xr-x   - root supergroup          0 2019-09-23 11:04 /topics/test_hdfs/f1=value1
drwxr-xr-x   - root supergroup          0 2019-09-23 11:04 /topics/test_hdfs/f1=value2
drwxr-xr-x   - root supergroup          0 2019-09-23 11:04 /topics/test_hdfs/f1=value3
drwxr-xr-x   - root supergroup          0 2019-09-23 11:04 /topics/test_hdfs/f1=value4
drwxr-xr-x   - root supergroup          0 2019-09-23 11:04 /topics/test_hdfs/f1=value5
drwxr-xr-x   - root supergroup          0 2019-09-23 11:04 /topics/test_hdfs/f1=value6
drwxr-xr-x   - root supergroup          0 2019-09-23 11:04 /topics/test_hdfs/f1=value7
drwxr-xr-x   - root supergroup          0 2019-09-23 11:04 /topics/test_hdfs/f1=value8
drwxr-xr-x   - root supergroup          0 2019-09-23 11:04 /topics/test_hdfs/f1=value9
```

N.B: Control Center is reachable at [http://127.0.0.1:9021](http://127.0.0.1:9021])
