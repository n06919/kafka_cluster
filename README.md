# Kafka cluster with KRaft 

```
$ git clone https://github.com/n06919/kafka_cluster.git 
$ cd kafka_cluster
$ cp -R server ~/workspace/kafka_2.13-3.8.0/
$ cd ~/workspace/kafka_2.13-3.8.0/
```

## common
```
KAFKA_CLUSTER_ID="$(bin/kafka-storage.sh random-uuid)"
echo $KAFKA_CLUSTER_ID
```
## server-1
```
# 터미널 새창-1
KAFKA_CLUSTER_ID=<KAFKA_CLUSTER_ID>

# Format Log Directories
$ cd ~/workspace/kafka_2.13-3.8.0/
$ ./bin/kafka-storage.sh format -t ${KAFKA_CLUSTER_ID} -c server/kafka-server1/config/server.properties

# Start the Kafka Server
$ export LOG_DIR=./server/kafka-server1/logs
$ ./bin/kafka-server-start.sh server/kafka-server1/config/server.properties
```

## server-2
```
# 터미널 새창-2
KAFKA_CLUSTER_ID=<KAFKA_CLUSTER_ID>

# Format Log Directories
$ cd ~/workspace/kafka_2.13-3.8.0/
$ ./bin/kafka-storage.sh format -t ${KAFKA_CLUSTER_ID} -c server/kafka-server2/config/server.properties


# Start the Kafka Server
$ export LOG_DIR=./server/kafka-server2/logs
$ ./bin/kafka-server-start.sh server/kafka-server2/config/server.properties
```

## server-3
```
# 터미널 새창-3
KAFKA_CLUSTER_ID=<KAFKA_CLUSTER_ID>

# Format Log Directories
$ cd ~/workspace/kafka_2.13-3.8.0/
$ ./bin/kafka-storage.sh format -t ${KAFKA_CLUSTER_ID} -c server/kafka-server3/config/server.properties


# Start the Kafka Server
$ export LOG_DIR=./server/kafka-server3/logs
$ ./bin/kafka-server-start.sh server/kafka-server3/config/server.properties
```