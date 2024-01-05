# CountingProducerInterceptor

The demo print the number of records and acknowledgement that are produced in last interval

## Configurations:

```
mvn clean package

```

```
export CLASSPATH=$CLASSPATH:~./target/kafka_CountingProducerInterceptor-1.0-SNAPSHOT.jar
```

Create a ./tmp/producer.config without configurations:

```
interceptor.classes=<your directory of CountingProducerInterceptor>
counting.interceptor.window.size.ms=10000
```

example:

```
interceptor.classes=com.quangtn.github.kafka.interceptors.CountingProducerInterceptor
counting.interceptor.window.size.ms=10000
```

```
kafka-console-producer.sh --broker-list localhost:9092 --topic interceptor-test --producer.config /tmp/producer.config
```
