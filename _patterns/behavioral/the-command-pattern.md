---
layout: article
title:  The Command Pattern (draft)
---

The simplest interaction between two classes is when one class encapsulates another class and invokes its methods. The former can be named as the Invoker class while the former can be named as the Receiver class.

![]()

Notice that in this configuration both Invoker and Receiver are coupled. Not only the Invoker has to know that the Receiver exists but the execution of the method occurs after the order has been given by the Invoker.

The Invoker is effectively coupled with who executes the method and it is also coupled with when the method is executed (following its request).

One way of breaking this coupling is to create another class that encapsulates the requests. This method usually has the name of Command and usually provides an execute() method.

![]()


The Command Pattern also allows several use cases to be implemented. For example:

- Replay commands
- Undo
- Actor model
