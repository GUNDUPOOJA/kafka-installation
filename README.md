# kafka-installation
This repo is all about installing kafka and doing a simple task.

# Installation steps
- First download the latest kafka release from this link
- [link](https://kafka.apache.org/quickstart)
- Save the tar file in C drive
- Now, open gitbash and run the following commands to extract the tar file and change directory.

```
$ tar -xzf kafka_2.13-2.7.0.tgz
```
```
$ cd kafka_2.13-2.7.0
```
- To start the kafka environment
- Open powershell in C:\kafka_2.13-2.7.0 folder.

- Use different powershell window for smooth process

1. Start the zookeeper service using this command (Use different powershell window)
```
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```

2. Start the kafka service( Use different window)
``` 
.\bin\windows\kafka-server-start.bat .\config\server.properties
```
- Once all services have successfully launched, you will have a basic Kafka environment running and ready to use.

3. Create a topic name to store all your events in kafka environment (Here my topic name is bearcat-msgs)- Use a different powershell window
```
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --create --topic bearcat-msgs
```
```
.\bin\windows\kafka-topics.bat --zookeeper localhost:2181 --list
```
4. Run Kafka Producer (will provide a > prompt for writing messages)
```
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic bearcat-msgs
```
- You can terminate using Cntrl+ C after writing messages.

5. Run Kafka Consumer (to show messages that you have written from the beginning)
``` 
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic bearcat-messages --from-beginning
```


