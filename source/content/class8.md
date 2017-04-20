class: center, middle

# Event Emitters
---
class: center, middle
![img](http://i.imgur.com/SuH6qS6.gif)

---
## Steps

- Step 1 : Emitter setup
- Step 2 : Socket IO
- Step 3 : Project Structure
- Step 4 : Return Promises

---
class: middle
## What are events?
Certain kinds of objects (called "emitters") periodically emit named events that cause Function objects ("listeners") to be called.

---
class: middle
## What are events?

In NodeJs, any object that emits an event is an instance of the EventEmitter class which exposes 2 important functionalities:

- The ability to trigger events using eventEmitter.emit(someEvent, optionalData)
- The ability to assign one or more event handlers to a specific event using eventEmitter.on(someEvent, eventHandler)

---
class: center, middle
## Where have we seen it before?
```js
// Jquery
element.on('click',function (event) {
  // Do something
})

// Sockets
io.on('connection', function(socket){
  //Do something
})

```

---
class: center, middle
## Let's code
