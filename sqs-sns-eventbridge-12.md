# SQS, SNS and Event-Bridge



## SQS

- `Simple Queue Service`
- Fully managed message queuing for `microservices`,`distributed systems` and `serverless` applications.
- Suitable of `1:1`

- Main concepts in SQS

    - **Queues**
        - Queue is temporary holding point.
        - `FIFO` but `order is not guaranteed ` unless you specified during the configuration steps while creating the queue.

    - **Messages**
        - messages can be any data that you want to transmit between components of your application
        - `text`,`json`,`blob`,`xml` etc

    - **Polling**
        - mechanism by which consumers(or subscriber,receiver) check a message queue for new messages.( check in queue if there is any message )

    
#image


## SNS

- `Simple Notification Service`
- fully managed `messaging service` provided by Amazon Web Services (AWS). 
-  It enables the distribution of messages or notifications to a distributed set of recipients or endpoints via multiple communication protocols. `HTTP/HTTPS`,`SMTP` etc
- Suitable of `1:M`
- Main concepts in SNS

    - **Topics**
        - In SNS, message are published to topics.A topic is an access point for allowing `recipients` to dynamically receive messages.

    - **Messages**
        - messages can be any data that you want to transmit between components of your application
        - `text`,`json`,`blob`,`xml` etc

    - **Publish/Subscribe (PubSub)**
        - Publisher are entities that `send messages` to `SNS topics`.
        - These entities could be `applications`,`services` or `other aws resources ` that generate message

        - Subscribers are entities that `receive message` from `SNS topics`.
        - These entities could be `AWS Lambda functions`, `Amazon SQS queues`,`HTTP/HTTPS` endpoints,`email addresses` and more.


    - **Fan-out Pattern**: SNS enables the fan-out pattern, where a `single message` can be delivered to `multiple subscribers `(endpoints) simultaneously.


#Image1


- enter the topic and exit topic very quickly unlike SQS.
- services are subscribe to the topics and SNS deliver the identital copies to the subscribed services and go next 


- lets say accountingservies has bad deployment and it goes down,`what happen to the messages that has been published to ordertopic while accountingservies is down?`
    - have to depend on Retry mechanism of SNS, what if service is down for may be more than hours and even days?
        - `it may lose some data ` in some cases it is not even acceptable for teir 1 service to lose the data.

- `one of the solutions` is to use `SQS queue`


#image2



## EventBridge

- EventBridge is a serverless service that` uses events `to `connect application components together`, making it easier for you to build scalable` event-driven applications`.

- Main concepts in EventBride

    - **Message Bus/ Event Bus**
        - An event bus is a central hub for ingesting and distributing events.
        - Can be default or custom
    - **Events**
        - Events are small JSON-formatted messages that represents a change in state or an occurance.
        - Events can be produced by aws services, custom applications, or third-party SaaS

    - **Rules**
        - Event Rules define the `conditions` under which`events `are `routed` to` targets`.

    - **Targets**
        - Targets are the endpoints where events are sent.
        - Example of targets include `AWS Lambda functions`, `Amazon SNS topics`, `AWS Step Functions.`

- Amazon EventBridge allows up to 5 targets per rule.

#img



## use case (which to use where)


#img