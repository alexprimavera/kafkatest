
## Connect to Docker
- connect to the docker instance: docker exec -it -w /opt/kafka/bin kafka sh


## Topics
- create topic: ./kafka-topics.sh --bootstrap-server broker:9092 --topic myTopic --create --partitions 3 --replication-factor 1 --command-config /etc/kafka/secrets/config.properties
- list topic: ./kafka-topics.sh --bootstrap-server broker:9092 --list
- delete topic: ./kafka-topics.sh --bootstrap-server broker:9092 --delete --topic my_topic

## Producer
- start producer: ./kafka-console-producer.sh --bootstrap-server broker:9092 --topic my_topic

## Consumer
- start consumer: ./kafka-console-consumer.sh --bootstrap-server broker:9092 --topic my_topic
- from beginning: ./kafka-console-consumer.sh --bootstrap-server broker:9092 --topic my_topic --from-beginning
- formatted messages: ./kafka-console-consumer.sh --bootstrap-server broker:9092 --topic my_topic --property print.timestamp=true --property print.key=true --property print.value=true --from-beginning
