---
permalink: /docs/ftw-actor-connector/
layout:    docs
title:     Actor Connector
menu:      Actor Connector
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

Considering the `Actor Instance` as a node within an `Actor Context`,
one might consider how such nodes (and other nodes in the network 
capable of communicating with Actors) interact with one another.

The role of the `FTW Actor Connector` is to conceptually act as a
link between nodes, enabling them to interact with one another.



is to act as a language binding for LabVIEW that defines the interface,
or API, by which an Actor Instance of the same type will interact.

Why in the world would one need an Actor Connector mirroring
functionality of an Actor Instance, especially when taking on
the responsibility and point of maintenance of synchronizing the two?

For a few reasons:
* fundamentally, pieces of a system or application that need other
pieces - say, a ContactResistanceMonitor that needs both a CurrentSource
instrument and a Voltmeter instrument - don't necessarily care about
driver or implementation details of instrumentation, but just care about
the value.
* incidentally, the different nodes in the system may not be
  within the same thread and call stack, the same same application instance,
  the same operating system user space, the same machine, the same subnet,
  or even the same intranet.
* incidentally, the different nodes may not even be within the same
  type system, or even language, or endianness, or byte-packing boundaries,
  or even quantization of "bits"!
  
For this reason, the Actor Connector provides a degree of indirection
from the Actor Instance, allowing an Actor Instance written in LabVIEW
to be invokable natively from any arbitrary node capable of sending
and receiving messages based on latest-greatest industry-standard types.

This degree of indirection may also be used to write different interfaces
for different purposes. For instance, a "basic" connector to an actor service
may have just a few executive methods, while an "advanced" connector might
expose more control. Similarly, since concrete instances of connectors derive
from the base FTW Actor Connector, you may define additional overrides and
subclasses to extend your own Connectors.

The Actor Connector encapsulates the dirty details of both Message
Serialization and Message Transport to any client, including other
languages and web browsers.

The Connector defines tasks such as:
* how to connect to an Actor Instance given the URI of that instance
  inbox
* what message types that Actor reacts to (including fanning out
  parameters sent in the message body as inputs on the connector pane),
  and also expected return types (again, fanning out response fields as ConPane
  outputs)
* how to disconnect from an Actor Instance

Many names were considered for this concept of "Actor Connector", including:

* Actor API, since from the outside looking in, 
* ActorRef or ActorReference (this is what Akka uses)
* Actor Binding
* Actor Client
* Actor Alias
* Actor ...

As of writing, "Actor Connector" was chosen, 

Nominally, the class is called an "Actor Connector", and once instantiated
as an object is an "Actor Connection" (even if not yet connected).

{ include note.html type="warning" title="UTF-8 Character Encoding Warning" text="If you use UTF-8 encoding, make sure that no <code>BOM</code> header characters exist in your files or very, very bad things will happen to Jekyll. This is especially relevant if you’re running <a href='../windows/'>Jekyll on Windows</a>." }

{ include note.html type="notice" title="ProTip™: Front Matter Variables Are Optional" text="If you want to use <a href='../variables/'>Liquid tags and variables</a> but don’t need anything in your front matter, just leave it empty! The set of triple-dashed lines with nothing in between will still get Jekyll to process your file. (This is useful for things like CSS and RSS feeds!)" }

## Does every `FTW Actor Instance` also need a connector?

No. A `FTW Actor Instance` selectively declares (or chooses not to declare!)
which of its inboxes will be listening for incoming requests at which particular
inbox addresses.

Additionally, it declares the subset of messages to which it will respond.

## Creating a new Actor Connector

To create a new Actor Connector

It is not explicitly necessary to create a new Actor Connector
for each Actor Instance type in an application. If the Actor Instance
only exposes a small set of messages, and especially if the messages
have a simple or no payload, the base class FTW-Actor-Connector may be
used 

## Ask XNode

Cluster in, with label equalling the name, of message to send.

## Poison Pill

Actor Instances exist as independent nodes within their Actor
Context, and are nominally orphaned in space and time unless
the communication medium remains healthy and responsive.

## Pick one: at most once, or at least once

Messages travelling through a lossy medium are not guaranteed to arrive;
we assume there does not exist such thing as "reliable delivery" of any
one message as it exists on the wire.

However, middleware can attempt to reasonably abstract this lossiness
from the application developer, which is what FTW attempts to do.


## Methods

### Connect (FTW-Actor-Connector-Connect.vi)

### Disconnect (FTW-Actor-Connector-Disconnect.vi)