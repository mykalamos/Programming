# Restful Web API Design
https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design

Well designed API should support
1. Platform independence - agnostic to API implementation. 
  - Agree on data exchange format
3. Service evolution - API add functionality independent of client.
  - Discoverable by client

## What is REST
- Representational State Transfer
- Architectural approach to building web services
- Independent of underlying protocol e.g. HTTP
- Designed around _resources_
  - A resource has an _identifier_
- Exchange of representation of resources e.g. JSON as exchange format
- Uniform interface
- Stateless
  - Requests should be independent and can occur in any order
  - No affinity required between client and server
- Driven by hypermedia links
