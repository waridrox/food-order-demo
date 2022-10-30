Event-driven scalable backend system for a food ordering app. 
Events considered such as:
* Order being placed.
* Order being confirmed.

These events are writtent to Apache Kafka which is a central bus for all moving data. Other systems, such as the transaction system or the email system, will be built on top of Apache Kafka. They will subscribe to different Kafka topics that they are concerned with, and process in real time as these messages are written to Kafka. 

`kafka-python` is used to hook up a locally running Kafka instance and the Python code. 

Given the decoupled nature, the system should be highly scalable. We can scale up or down individual components as and when required. These individual components can either be microservices or some stream processing jobs.

Given the persistence of Kafka, if there is an issue with any downstream or upstream system, the system will not suffer from any data loss.