class: center, middle

# Chat Application


---
class: center, middle
![img](https://media.giphy.com/media/m12EDnP8xGLy8/giphy.gif)
### Web Sockets
**Real-Time Communication**

---
## Concepts
- Websockets
- Databases: Relational/Non-Relational
- MongoDb
- Node Config File

---
class: center, middle

### WebSockets is an advanced technology that makes it possible to open an interactive communication session between the user's browser and a server. 
---
class: middle

## Interfaces
### 1. WebSocket
Primary interface for connecting to a WebSocket server and then sending and receiving data on the connection

### 2. CloseEvent
Sent by the WebSocket object when the connection closes

### 3. MessageEvent
Sent by the WebSocket object when a message is received from the server
---
class: middle, center

### [WebSockets API: MDN](https://developer.mozilla.org/en-US/docs/Web/API/WebSockets_API)
---

class:middle , center
### REST
![diag](https://i.stack.imgur.com/xuzzd.png)

---

class: middle, center
### Websockets
![diag](https://image.slidesharecdn.com/whatarewebsockets-140911173054-phpapp01/95/what-are-websockets-4-638.jpg?cb=1410456718)

---
class: middle, center
## [REST vs WebSockets Benchmarks](http://blog.arungupta.me/rest-vs-websocket-comparison-benchmarks/)

---
class: middle, center
![mongodb](https://www.nop4you.com/content/images/thumbs/0001494_search-engine-powered-by-mongodb.jpeg)

Finally!
---
class: middle, center
## Relational vs Non-Relational Databases

Relational databases represent and store data in tables and rows. 

They're based on a branch of algebraic set theory known as relational algebra. 

Non-relational databases like MongoDB represent data in collections of JSON documents. 

The Mongo import utility can import JSON, CSV and TSV file formats.
---
class: middle

**Relational databases are good for**
- For applications that involve the management of several transactions
- For applications that are heavy into data analysis.
- Examples: MySQL, PostgreSQL and SQLite3 

But... relational databases were not initially created with the OOP languages in mind.
---
class: middle

**Non-Relational databases are good for**
- If you’re dealing with a phenomenally huge amount of data, it can be way too tedious, and the probability of error (in the form of an ORM Impedance Mismatch issue) increases. 
- A non-relational database just stores data without explicit and structured mechanisms to link data from different tables (or buckets) to one another.

[Read More](https://www.mongodb.com/scale/relational-vs-non-relational-database)
---
class: middle, center

![mongoose](http://www.quickanddirtytips.com/sites/default/files/images/7832/plural-of-mongoose.jpg)
---
class: middle, center

![mongoose](https://velopert.com/wp-content/uploads/2016/02/%EC%9D%B4%EB%AF%B8%EC%A7%80-13.png)
---
## Code
- Starter-Code : Boilerplate
- Step 1 : Chat CSS + SocketIO Connection
- Step 2 : MongoLab Connection + Message JSON
- Step 3 : Store Data

---
class: center, middle

Q- How many bits of bait does a programmer need to go fishing?

A- At least 8, or else the fish won’t byte