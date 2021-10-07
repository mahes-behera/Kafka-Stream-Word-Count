# Kafka-Stream-Word-Count
Steps to run Word count - Stateful stream
1. Create 2 topics inputTopic and outputTopic
2. Use this command to create topic --> kafka-topics.bat --zookeeper localhost:2181 --topic outputTopic --create --partitions 3 --replication-factor 1
3. Start producer -> kafka-console-producer.bat -broker-list localhost:9092 -topic inputTopic
4. Start Consumer -> kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic outputTopic --from-beginning --formatter kafka.tools.DefaultMessageFormatter --property print.key=true --property print.value=true --property key.deserializer=org.apache.kafka.common.serialization.StringDeserializer --property value.deserializer=org.apache.kafka.common.serialization.StringDeserializer
5. Run the standalone Stream word count program - WordCountExample.java
6. Type some message in producer console --> run WordCountExample.java --> check output in consumer console 
