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

{% include note.html type="note" title="Note" body="Since a message payload is represented only by ordered bytes, be careful making assumptions if using binary payloads. Depending on the platform, endianness and packing boundaries might be different, so be mindful the receiving endpoint unflattens as the sending endpoint flattened. To avoid such issues and to promote interoperability, Featherweight uses JSON as the message payload serialization protocol." %}

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

{% include note.html type="note" title="Note" body="It is not an absolute rule for message elements to possess by-value semantics. It is valid (and sometimes useful) to flatten a reference as a string (such as the form `0x00000000`), but be mindful of implications such as scope and lifetime when dereferencing outside the original context." %}

## Actor Request

The heart of messaging between entities in Featherweight is the Actor Request.

An Actor Request is nominally sent from an Actor Connector to an Actor Instance.

For brevity, we sometimes refer to Actors as "talking to each other". More precisely,
an Actor Instance (or other entity) owns a Connector, and it's the Connector that
"talks" with the other Actor.

### Requests echo fields that are not consumed

When an Actor receives a Request, is has the opportunity to read values from the
Request as JSON fields. The receiving Actor has the option of consuming the value
on read, and all values not consumed will be echoed back to the originating
requestor.

{% include note.html type="warning" title="Consume Request fields to preserve resource usage" body="If values are unintentionally not consumed, they will require unnecessary overhead serializing and transmitting back to the requestor. This is usually negligible, but could become expensive for particularly large payloads." %}

#### Design pattern: future tokens
