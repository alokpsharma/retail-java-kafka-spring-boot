# Order fulfillment sample application demonstrating concepts in the context of DDD and Microservices. 

This sample application shows how to implement

* a simple order fulfillment system

in the context of

* Domain Driven Design (DDD)
* Event Driven Architecture (EDA)
* Microservices (µS)


# Overview

## Concrete technologies/frameworks:

* Java
* Spring Boot
* Spring Cloud Streams
* Camunda
* Apache Kafka



# Run the application

* Download or clone the source code
* Run a full maven build

```
mvn install
```

* Install and start Kafka on the standard port
* Create topic *"flowing-retail"*

```
kafka-topics.sh --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic flowing-retail
```

* You can check & query all topics by: 

```
kafka-topics.sh --list --zookeeper localhost:2181
```

* Start the different microservices components by Spring Boot one by one, e.g.
    
```
mvn -f checkout exec:java
...
```

You can also import the projects into your favorite IDE and start the following class yourself:

```
checkout/io.flowing.retail.java.CheckoutApplication
...
```

* Now you can place an order via [http://localhost:8090](http://localhost:8090)
* You can inspect insided of Order via [http://localhost:8091](http://localhost:8091)
* You can inspect insides of Payment via [http://localhost:8092](http://localhost:8092)
* You can inspect all events going on via [http://localhost:8095](http://localhost:8095)

