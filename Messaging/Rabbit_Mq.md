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
- Exchange
  1. Receives messages from producers
  2. Pushes them to queue(s)
- Exchange types
  - Direct
  - Topic
  - Headers
  - Fanout
