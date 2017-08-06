# Kafka Docker Sample
This a docker compose file to setup a single broker install of Kafka. It uses these images:

- wurstmeister/zookeeper
- wurstmeister/kafka

## Usage
```
git clone https://github.com/fabianmagrini/docker.samples.git
cd docker.samples/kafka
docker-compose up
```

## Test an Example for DotNet

### Confluent Kafka Dotnet
```
git clone https://github.com/confluentinc/confluent-kafka-dotnet.git
```

### Run Producer
```
cd confluent-kafka-dotnet/examples/SimpleProducer
dotnet restore
dotnet run 127.0.0.1:9092 testtopic
```

### Run Consumer
```
cd confluent-kafka-dotnet/examples/SimpleConsumer
dotnet restore
dotnet run 127.0.0.1:9092 testtopic
```
