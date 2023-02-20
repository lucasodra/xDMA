# Distributed Messaging Application
The distributed messaging application is a Java-based system that uses RabbitMQ and Spring Microservices to implement a publish-subscribe pattern for broadcasting messages to multiple subscribers. The system is designed for high throughput, scalability, and fault tolerance, and can be easily extended and customized to handle different types of messages and routing patterns.

## Features
- High throughput: the publisher uses multithreading to generate messages in parallel, allowing the system to handle high message rates.
- Scalability: the use of RabbitMQ and Spring Microservices allows the system to be easily scaled up or down by adding or removing subscribers.
- Fault tolerance: the use of the publish-subscribe pattern and RabbitMQ ensures that messages are delivered even if one or more subscribers are unavailable.
- Flexibility: the system can be extended with additional publishers or subscribers, and can be easily customized to handle different types of messages or routing patterns.

## Architecture
The messaging application consists of the following components:

- Publisher: A Java application that generates messages and publishes them to a RabbitMQ exchange using the Spring AMQP library. The publisher uses multithreading to generate messages in parallel and achieve high throughput.
- RabbitMQ: A message broker that receives messages from the publisher and distributes them to subscribers based on the routing keys of the messages. RabbitMQ is used to implement the publish-subscribe pattern, allowing multiple subscribers to receive messages from the same exchange.
- Subscribers: Multiple Java applications that receive messages from RabbitMQ using the Spring AMQP library. Each subscriber runs in its own thread and can process messages independently.
- Spring Microservices: A Spring-based application that manages the lifecycle of the publisher and subscribers, and provides a REST API for controlling the system. The Spring application uses Spring Boot for rapid development and configuration, and Spring Cloud for service discovery and load balancing.

## Installation
To install and run the messaging application, follow these steps:

1. Install RabbitMQ on your system and ensure it is running.
2. Clone the repository to your local machine.
3. Build the project using Maven: mvn clean package
4. Start the Spring Microservices application: java -jar target/messaging-1.0-SNAPSHOT.jar
5. Start one or more subscribers: java -jar target/messaging-1.0-SNAPSHOT.jar --subscriber


## Usage
To use the messaging application, follow these steps:

1. Send a message to the publisher using the REST API: POST /message?body=Hello+world!
2. The publisher will generate a message and publish it to RabbitMQ.
3. The subscribers will receive the message and process it independently.

You can use the REST API to control the system, including starting or stopping the publisher or subscribers, adding or removing routing keys, and viewing system status and statistics.

Contributing
If you would like to contribute to the messaging application, please follow these guidelines:

Fork the repository and create a new branch for your changes.
Make your changes and ensure that all tests pass.
Submit a pull request with a description of your changes and any relevant documentation or testing instructions.
License
The messaging application is licensed under the MIT License. See LICENSE for details.
