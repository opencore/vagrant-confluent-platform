# vagrant-confluent-platform
Vagrantfile to start a virtual machine running the confluent platform: zookeeper, kafka, schema registry and confluent control center.

To use simply clone the repository and run:

```
vagrant up
```

The machine exposes the following ports:

- 2181: Zookeeper
- 8081: Schema registry
- 9021: Confluent Control Center
- 9092: Kafka
