FROM store/oracle/serverjre:8
ENV ZOOKEEPER zookeeper
RUN yum install -y tar gzip &&\
    curl http://mirror.netinch.com/pub/apache/kafka/0.10.2.1/kafka_2.12-0.10.2.1.tgz | tar -xvz -C /opt
WORKDIR /opt/kafka_2.12-0.10.2.1
CMD ["sh", "-c", "./bin/kafka-server-start.sh config/server.properties --override zookeeper.connect=${ZOOKEEPER}:2181 --override listeners=PLAINTEXT://0.0.0.0:9092"]
