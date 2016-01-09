# Kafka

Kafka is a framework to handle real time data/feeds. In this repository, it is gonna show how to install this powerful framework, and run a typical example in the Ubuntu OS.

1. It needs to install the latest version of Java(assuming everyone knows how to do that in Ubuntu)
2. Download the lastest stable release of Kafka "http://kafka.apache.org/downloads.html". Use this URL to download the binary file, similar to  "kafka_2.11-0.9.0.0.tgz". In they change the name of the download page, simply use google to find it out. After finishing the download process, create a folder and name it whatever as the uesr like, I named it as Kafka, and extract that downloaded file into that folder.
3. Use timinal to go to that folder, in my case Kafka, and type "export KAFKA_HOME=/Kafka/kafka_2.11-0.9.0.0", depending on the version of the kafka folder, it can change over time. Then hit enter. And type "export PATH=$PATH:$KAFKA_HOME/bin"
4. Go to the kafka_2.11-0.9.0.0 folder and start to run the zookeeper by typing "bin/zookeeper-server-start.sh config/zookeeper.properties", and hit enter. 
5. Open another terminal to start the broker. Go to the same folder and type "bin/kafka-server-start.sh config/server.properties" and hit enter.
6. Now the broker is running and it must have a topic for the procuder and comsumer know where to look at in the broker. In order to create a topic, open another teminal which is the third terminal and go to the same folder. Type "bin/kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic firsttopic".
7. To create the producer/message sender, use the third terminal and type "bin/kafka-console-producer.sh --broker-list localhost:9092 --topic firsttopic".Now, you can type any messages in the terminal and those messages will be saved in the broker waiting for the consumer to read them. Type "it is good" and hit enter.
8. Open the fourth terminal, go to the same folder, and type "bin/kafka-console-consumer.sh --zookeeper localhost:2181 --topic firsttopic --from-beginning". You will see a message you gave in the third terminal.

The basic setup is pretty straight forword. that is of course more to discover about the Kafka. However, here shows how the Kafka works.
