
02-01-2026 Notes:

Session 1 Notes :

- Concepts : Database, Caching, Scaling, Delegation, Concurrency, Communication

- Design an offline/online indicator , Design a multi user blogging platform

- Schema ( User-id, Status )
    -    (user) - (API server) - (Database)
 
- API - Get ----> Single Get vs Bulk Get [ Batch Get is faster ]
- Storage Space for the Table [ user- 4 B + Status - 4 B ] - 1 Billion entires - 8GB

- Read / Write Access Pattern
- Insert / Upsert

- Update ( heartbeat every 30 seconds ) - Push/Pull - Client update HB every 30 sec to
- Schema ( user-id, heartbeat )
  If there is no heartbeat update in the last 30s , the user is considered offline, else online

- Create a cron job to delete the inactive users, have a TTL and database will automatically delete if TTL expires.
- Store only the users who are online with a TTL value. If TTL expires, database will automatically deleted
- [ Key-Value Database ]

- Redis vs DynamoDB - Depends on speed, scale, open source, vendor lock-in

- Number of API requests to update heartbeat ---1 million Users - 10 s update - 6 updates / minutes - 6 million updates / minute

- Concept of Connection Pooling :
   - Instead of opening a individual connection to the DB at every request, we maintain a pool of connections
     in a bounded queue. If the queue is empty the requests wait, else pick the connection object, satisfy the
     request and respond back.
  - Avoid Database connection bottlenecks at scale
  - TCP connection

 Caching as a technique rather an as something that is stored in RAM
 
 - Concept of Debouncing :
   - When there are multiple requests to the cache at the same time, one goes to DB, others wait ( reduces disk i/o, cpu computation)

 - Concept of Load leak:
   - Even when there is a cache hit, leak some load on the DB
  
Session 2 Notes :

- Caching at various different places - RAM, DISK
  At Browser, CDN, LB , API Server, Database

- Scaling - Always think Bottom Up
-  Database -  Vertical Scaling, Horizontal Scaling - Read Replicas, Sharding
-  Routing requests when you replicas , shard need knowledge of the Database topology
-  Abstract it from the Api Server using RDS Proxy, Proxy SQL ( topology discovery , changes are offloaded to the proxy which maintainis
  the connection objects to the DB )


  
  
