# Docker-kafka

Docker-kafka is a docker-compose file for kafka including Dockerfiles for openJDK and oracleJDK. In order to use the oracleJDK image you have to login to Dockerhub and get the image from the Docker store. Change the "volume:" in the docker-compose.yaml according to your topology target folder.

### Usage

```sh
$ docker-compose up
```
Creating a topic, a producer and consumer:
```sh
$ docker-compose run --rm kafka-cmd ./bin/kafka-topics.sh --zookeeper kafka-zookeeper:2181 --create --topic testtpoic --partitions 1 --replication-factor 1
$ docker-compose run --rm kafka-cmd ./bin/kafka-console-producer.sh --broker-list kafka-broker:9092 --topic testtopic
$ docker-compose run --rm kafka-cmd ./bin/kafka-console-consumer.sh --bootstrap-server kafka-broker:9092 --topic testtopic
```

