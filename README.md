# Performance Test : Mongo vs Cassandra
---

## Description
---

### A very simple scenario.

#### basic
System has products and users.
Users can have a like on products.
Timestamp is recorded when user like products for ordering.

#### query
Given a product id, found the most recent 20 likes, etc.

---
## File descriptions
---
TBC

---
## Schema
---

### mongo

###### Product
|name|type|index|
|:-|:-:|:-:|
|id|ObjectID|primary key|
|number|int|

###### User
|name|type|index|
|:-|:-:|:-:|
|id|ObjectID|primary key|
|number|int|

###### Like
|name|type|index|
|:-|:-:|:-:|
|id|ObjectID|primary key|
|product|DBRefs|index|
|user|DBRefs|
|ts|timestamp|index|

### cassandra

###### Product
|name|type|index|
|:-|:-:|:-:|
|id|int|primary key|
|number|int|

###### User
|name|type|index|
|:-|:-:|:-:|
|id|int|primary key|
|number|int|

###### Like
|name|type|index|
|:-|:-:|:-:|
|product|int|primary key|
|user|int|
|ts|timestamp|primary key|
