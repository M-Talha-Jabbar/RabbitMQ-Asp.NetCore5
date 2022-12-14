# RabbitMQ
![Capture](https://user-images.githubusercontent.com/76180043/188571263-94d2ebe9-d304-4d7c-9dbe-99f7af6268b6.PNG)

Producers don't have to wait for messages to be delivered & Consumers don't have to wait until messages get sent.

An exchange is what a producer always sends its messages to. So, Producer emit messages to exchange and Consumer receive messages from queue.

Binding connects an exchange with a queue using binding key.

RabbitMQ gives us a lot of flexibility in how we setup our message broker. We can duplicate messages by sending them from exchange into multiple queues or we can make sure only one queue ever get a message from an exchange.

Every producer and consumer should open a single TCP connection to our RabbitMQ broker. A connection however can have multiple channels. By using a connection with multiple channels, a producer for example might be able to produce and push messages onto our message broker using different threads but because each thread is a different channel, these messages are isolated from one another. By using channels and not opening multiple connections we can save a lot of resources. The same is true for consumers who will only have one connection but might have multiple channels. 

## Exchange Types
1) Fanout Exchange
2) Direct Exchange
3) Topic Exchange
4) Header Exchange
5) Default (nameless) Exchange - Special exchange created by RabbitMQ which compares routing key with queue name instead of comaparing routing key with binding key.
