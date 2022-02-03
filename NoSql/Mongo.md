# MongoDb
https://www.mongodb.com/basics

## Documents
- Stores as JSON documents
- Natural mapping to objects in code
- Fields can vary between documents
- Data can be hierarchical
- Flexibility
  -  Complex fast-changing data from numerous source
- Converted to BSON (Binary Json)

## Collections
- Group of documents
- No enforcement of schema

## Replica Sets
- High availability built in
- 3+ MongoDb instances that continously replicate
- Redundancy, downtime protection

## Sharding
- Distributing data across multiple machines
- At collection level
  - Dcouments distributed across shards in the cluster

## Indexes
- Support for compound indexes on multiple fields

## Aggregation Pipelines
- Process, transform and analyze data of any structure at scale
