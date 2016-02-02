---
permalink: /docs/actor-message/
layout:    docs
title:     Actor Message
menu:      Actor Message
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

A Message represents an atomic unit of information that is sent
from one actor to another actor.

When sending a message, depending on may duplicate the message
at t

A Message conveys information by:

* its arrival
* implicitly, its failure to arrive within a certain time
* payload of bytes (optional, but typical)

If a message arrives at its destination, the transport has guaranteed
it is intact and not garbled. This includes preserving the exact byte order.

{ include note.html type="note" title="Note" text="Since a message payload is represented only by ordered bytes, be careful making assumptions if using binary payloads. Depending on the platform, endianness and packing boundaries might be different, so be mindful the receiving endpoint unflattens as the sending endpoint flattened. To avoid such issues and to promote interoperability, Featherweight uses JSON as the message payload serialization protocol." }

## Messages have By-Value Semantics

When a message is sent from one endpoint to another, no part
of the message should have a reference, pointer, or otherwise indirect
value.

This is for a few reasons:

* the scope, context, and environment of the remote actor

* assuming the reference could be dereference, to avoid resource contentions, such as:
** inter-actor mutexing
** livelock/deadlock
* the resource may  

{ include note.html type="note" title="Note" text="It is not an absolute rule to " }
