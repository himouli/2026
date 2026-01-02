
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

- 
