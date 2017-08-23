
## Commands vs Evets
- Commands are something we want to happen. Events are something that has happened [stackoverflow](https://stackoverflow.com/a/4964228)
- A Command is a request made to the system to do something. An event is something that happen and that cannot be changed. [Event-Sourcing-vs-Command-Sourcing](http://thinkbeforecoding.com/post/2013/07/28/Event-Sourcing-vs-Command-Sourcing)

## Event Sourcing
- _ is all about storing of facts. [Greg Young](https://youtu.be/JHGkaShoyNs)
- _ allows you to time travel. [Greg Young](https://youtu.be/JHGkaShoyNs)
- _ provides loss less transactional model, append-only, immutable. [Greg Young](https://youtu.be/JHGkaShoyNs)

## CQRS
- _ is a pattern that segregates the operations that read data (queries) from the operations that update data (commands) by using separate interfaces. [msdn](https://docs.microsoft.com/en-us/azure/architecture/patterns/cqrs)
- _ splits the application into two parts: the command-side and the query-side. The command-side handles create, update, and delete requests and emits events when data changes. / [microservices.io](http://microservices.io/patterns/data/cqrs.html)
- I've come to the conclusion that commands are redundant. They are simply events from your user, they did press that button. You should store these in exactly the same way as other events because it is data you don't know if you will want to use it in a future view. Your user did add and then later remove that item from the basket or at least attempt to. You may later want to use this information to remind the user of this at later date. [stackoverflow](https://stackoverflow.com/a/27225926)
