# mod9-publisher

1. **How much data will your publisher program send to the message broker in one run?**

    In one execution, the program sends 5 messages to the message broker. Each message contains a `UserCreatedEventMessage` struct with the following fields:
    
    - `user_id`: "1", "2", "3", "4", or "5"
    - `user_name`: "2306152166-Amir", "2306152166-Budi", "2306152166-Cica", "2306152166-Dira", or "2306152166-Emir"

    This means the publisher will deliver 5 distinct messages, each representing a user creation event, to the broker in a single run.

2. **The URL "amqp://guest:guest@localhost:5672" is the same as in the subscriber program. What does it mean?**

    This URL is the connection string used to access the RabbitMQ message broker. By using the same URL in both the publisher and subscriber:

    Using the same connection string ensures that both programs communicate through the same message broker and can exchange messages successfully.

## Running RabbitMQ as message broker.
![image1](mod9-1.png)

## Sending and processing event.
![image2](mod9-2.png)

When I run the publisher using ``cargo run``, the application sends 5 events to the RabbitMQ message broker. These events can then be consumed and processed by the subscriber.

# Monitoring chart based on publisher.
![image3](mod9-3.png)

# Simulation slow subscriber
![image4](mod9-4.png)



