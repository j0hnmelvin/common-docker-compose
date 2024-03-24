# apache-zookeeper-kafka-confluent-schemaregistry-restproxy

The Confluent REST Proxy provides a RESTful interface to an Apache Kafka cluster, making it easy to produce and consume messages, view the state of the cluster, and perform administrative actions without using the native Kafka protocol or clients.

## Publish Apache Avro Message Using REST Proxy

```
curl --location --request POST 'http://localhost:8082/topics/<TOPIC-NAME>' \
--header 'Content-Type: application/vnd.kafka.avro.v2+json' \
--data-raw '{
    "value_schema": <AVRO-SCHEMA>, OR "value_schema_id": <AVRO-SCHEMA-ID>,
    "records": [
        {
            "value": <AVRO-RECORD>
        },
        {
            "value": <AVRO-RECORD>
        }
    ]
}'
```