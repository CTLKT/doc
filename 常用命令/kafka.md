开启zookeeper

/app/zookeeper/zookeeper-3.4.8/bin/zkServer.sh start

关闭zookeeper

/app/zookeeper/zookeeper-3.4.8/bin/zkServer.sh stop

开启kafka

/app/kafka/kafka_2.12-3.0.0/bin/kafka-server-start.sh -daemon /app/kafka/kafka_2.12-3.0.0/config/server.properties

关闭kafka

/app/kafka/kafka_2.12-3.0.0/bin/kafka-server-stop.sh

查看所有topic

/app/kafka/kafka_2.12-3.0.0/bin/kafka-topics.sh --bootstrap-server hadoop01:9092 --list

创建first topic

/app/kafka/kafka_2.12-3.0.0/bin/kafka-topics.sh --bootstrap-server hadoop01:9092 --create --partitions 1 --replication-factor 3 --topic first

查看first topic

/app/kafka/kafka_2.12-3.0.0/bin/kafka-topics.sh --bootstrap-server hadoop01:9092 --describe --topic first

生成者

/app/kafka/kafka_2.12-3.0.0/bin/kafka-console-producer.sh --bootstrap-server hadoop01:9092 --topic first

消费者

/app/kafka/kafka_2.12-3.0.0/bin/kafka-console-consumer.sh --bootstrap-server hadoop01:9092 --topic first

/app/kafka/kafka_2.12-3.0.0/bin/kafka-console-consumer.sh --bootstrap-server hadoop01:9092 --from-beginning --topic first

/app/kafka/kafka_2.12-3.0.0/bin/kafka-console-consumer.sh --bootstrap-server hadoop01:9092 --topic first --partition 1

查看日志

vi /app/kafka/kafka_2.12-3.0.0/logs/kafkaServer.out

