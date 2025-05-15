# Advanced Programming Module 9 - Publisher
### Athazahra Nabila Ruby - 2306173113

> How much data your publisher program will send to the message broker in one run?
 
In a single execution, the publisher program will send five messages to the message broker. This is shown from the publish_event function being called five times in the main function, each with different data for each user. Each message is an instance of UserCreatedEventMessage containing values for user_id and user_name, such as "1", "2306173113-Amir" up to "5", "2306173113-Emir". All messages are sent to the "user_created" queue through the AMQP connection at amqp://guest:guest@localhost:5672.

> The url of: “amqp://guest:guest@localhost:5672” is the same as in the subscriber program, what does it mean?
 
The use of the URL amqp://guest:guest@localhost:5672 indicates that both the subscriber and publisher are connected to the same message broker, which is the AMQP server running locally on port 5672. Since both are connected to the same broker, messages sent by the publisher to a specific topic can be received by the subscriber listening to that topic. If the URLs were different, the publisher and subscriber would be on separate sessions or servers, and communication between them would not occur.