# Rabbit MQ
## Basics
- Message Broker
- Accepts and forwards messages (Post Office/Postman/PostBox all in one)
- Producing = Sending
- Consumer = Receiving
- Queue = Large message buffer
  - Many producers => 1 queue
  - Many Consumers <= 1 queue

## Rabbit ontology
- Connection
- Channel
- Queue
- Routing Key
- Bindings
  - Exchange <-> Queue
- Exchange
  1. Receives messages from producers
  2. Pushes them to queue(s)
- Exchange types
  - Default exchange (queue is routing key)
  - Direct
    - Binding exact match routing key
  - Topic
    - Like direct but uses wild cards
  - Headers
    - Message headers used for routing
  - Fanout
    - Copies to all queues
## Acknowledgements
- Consumer - delivery tag - unique on a channel
  - Must be acked on same channel
  - basic ack - positive - can discard
  - basic nack - negative - multiple
  - basic reject - negative - single
- Acks can be batched

## Durability
- Queue and messages need to marked as durable so they can be recreated if RabbitMq shutdown
