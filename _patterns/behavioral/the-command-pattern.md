---
layout: article
title:  The Command Pattern
---

The simplest interaction between two classes is when one class encapsulates another class and invokes its methods. The former can be named as the Invoker class while the latter can be named as the Receiver class.

![Invoker-Receiver-Relationship](/images/patterns/invoker-receiver.svg)

Notice that in this configuration both Invoker and Receiver are coupled. Not only the Invoker has to know that the Receiver exists to be able call *doSomething()* but also the execution of the same method occurs after the call has been triggered by the Invoker. The Invoker is coupled with **who** executes the call and with **when** the call is executed.

The command pattern breaks this coupling by encapsulating the request of the Invoker to the Receiver on its own objects. The object's class is commonly called Command and implements a method called *execute()* for its interface.

![Invoker-Command-Receiver-Relationship](/images/patterns/invoker-command-receiver.svg)

This configuration is functionally equivalent to the previous one if *createCommand()* not only creates the DoSomethingCommand but also calls its method *execute()*. The downside of course is the boilerplate required for the configuration.

However, there is a lot versatility that is gained from encapsulating the requests in a  Command object. The Invoker instead of executing the command directly can pass the Command objects to a command manager (CommandManager) responsible for handling the Commands. This opens the implementation of several use cases that were not possible before. 

For example, the CommandManager can store commands and execute/schedule them at a later time breaking the temporal coupling that existed before. 

If the commands are stored in a queue we can easily save an history of executed commands. Additionally, if each Command also maintains the state necessary to reverse its *execute()* method, for example in a method named *undo()*, we can implement multi-level undo funcionality. 

Also, Command objects can be consumed in parallel by a pool of threads optimizing the usage of computational resources. This is also the way we can implement lightweight threads without associated stacks.


