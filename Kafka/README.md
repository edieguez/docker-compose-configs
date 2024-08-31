# [Kafka](https://kafka.apache.org/documentation)

- [Kafka UI](http://127.0.0.1:8080)

## Documentation

- [Kafka UI](https://docs.kafka-ui.provectus.io/configuration/quick-start)

## Aliases

```bash
alias kafka-topics='docker compose exec kafka kafka-topics --bootstrap-server 127.0.0.1:9092'
alias kafka-console-consumer='docker compose exec kafka kafka-console-consumer --bootstrap-server 127.0.0.1:9092'
alias kafka-console-producer='docker compose exec kafka kafka-console-producer --bootstrap-server 127.0.0.1:9092'
alias kafka-consumer-groups='docker compose exec kafka kafka-consumer-groups --bootstrap-server 127.0.0.1:9092'
```

## Useful commands

> These commands rely on having the aliases defined

```shell
kafka-topics --list
kafka-topics --describe
kafka-topics --delete --topic $topic_name

# Simple message
kafka-console-producer --topic $topic_name

# Key value message
kafka-console-producer --property 'parse.key=true' --property 'key.separator=:' --topic $topic_name

# Consume messages
kafka-console-consumer --topic $topic_name

# Consume messages from beginning
kafka-console-consumer --from-beginning --topic $topic_name

# Consumer groups. Run multiple consumers to see the messages being distributed
kafka-console-consumer --group test-consumer-group --topic $topic_name
```

## Properties

- `--property parse.key=true` enables key, value messages
- `--property print.key=true` prints the key in the consumer output
- `--property key.separator=' = '` sets the key separator in the consumer output
- `--from-beginning` consumes messages from the beginning of the topic
