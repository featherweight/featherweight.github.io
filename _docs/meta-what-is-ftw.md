---
permalink: /what-is-featherweight/
layout:    docs
title:     What is FTW?
menu:      What is FTW?
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

Featherweight is a [design philosophy](/philosophy/).

Featherweight is also a collection of libraries for LabVIEW,
curated to [work well together as a framework](/ftw-as-a-framework/), but also designed
to be [individually accessible](/ftw-a-la-carte/) and useful for existing applications.

Featherweight is often abbreviated FTW. As in, CTRL+Space FTW.

The [Featherweight logo](/logo/) is a hummingbird. Lightweight for
dexterity, agility and speed.

* is  based on this principle;
* has no external dependencies;
* has reference designs for distributed systems;
* 
* forms an application microframework.

## Feature Highlights

### Actor Model and Reference Design

Featherweight offers an Actor Reference Design as an
application and system architecture model.

Many software development communities have moved toward
actor-oriented development. To list a few:

* Scala (and Java) - [Akka](http://akka.io/)
* C#/.NET - [Orleans](http://dotnet.github.io/orleans/) and [Akka.NET](http://getakka.net/)
* LabVIEW - [NI Actor Framework](https://decibel.ni.com/content/groups/actor-framework-2011)

To 

<a href="/actors/">Learn more about FTW Actors &rarr;</a>

### Messaging with Sockets

Featherweight brings the first library of its kind to LabVIEW,
consolidating many common messaging semantics and transport
mechanisms into a single coherent library.

Whether your actors are sending messages to each other in the
same application context, to other applications on the same computer,
to applications across a network or the internet, to a client running
in a browser, or to a binding written in another language, Featherweight
Sockets ensure that as your application requirements change, you won't
have to endure expensive refactors.

<a href="/concepts/messaging/">Learn more about sockets and messaging &rarr;</a>

### Idiomatic SQLite Binding

[SQLite](https://www.sqlite.org/about.html) is an incredibly
powerful embedded database engine. Featherweight wraps its
abilities with an idiomatic binding to the LabVIEW Block Diagram,
meaning 

<a href="/concepts/sqlite-tips/">Learn more about SQLite &rarr;</a>

### Idiomatic JSON Binding

In addition to being one of the most widely-supported data serialization
protocols, JSON Objects in Featherweight provide a dynamic
type container for most LabVIEW datatypes.

<a href="/concepts/json-tips/">Learn more about SQLite &rarr;</a>

## Fighting the Tide with Open Source

Software and computing are like a tide that is always rushing
out to open sea.

Things we create as developers are small vessels in this tide.
In order for our creations to retain value and not be pulled out
to sea is to put energy sailing against this tide. To avoid sinking
and abandoning ship, we must continually patch leaks and sometimes
bail buckets.

Open-source collaborative design is a source of energy for
our vessels. This energy is vastly more plentiful than what
our finite teams are able to create for ourselves.

But it can be hard to harness this energy. Especially in a
development environment and language that does not necessarily
readily integrate with other languages and software developers.

This is where Featherweight helps bridge the gap. By curating
a collection of powerful open source libraries written in ANSI C,
and wrapping them in native, idiomatic APIs for LabVIEW.

Applications built with Featherweight continue to grow in
capability and value, since Featherweight continues to upgrade
and update based on the best libraries available. 

## What skill level do I need to use Featherweight?

At least one Certified LabVIEW Architect (CLA) is recommended for project
teams using Featherweight.

This is not because Featherweight is too complex for those with less
experience to be successful. It is because Featherweight is designed
for building non-trivial sized applications and distributed systems
using LabVIEW, and this application area can be inherently complex.

One explicit design goal of Featherweight is to be usable for CLD-level
developers, and to provide a seamless learning experience from here to
CLA-level and beyond.

Advanced topics and complexity are often encapsulated within the framework,
yet not inaccessible or immutable.

Some self-assessments that might help understand the level of complexity
of FTW topics:

### Sockets

To fully grasp the `FTW Socket` libraries, it helps to understand
LabVIEW Notifiers, Queues, User Events, and Network Streams. Some questions
that are 

Where are each of these topologies used? What are some problems
you might encounter if the incorrect topology what chosen? In what ways is
asynchronous dataflow more difficult to develop, debug, and maintain than
synchronous dataflow?

What are the fan-in and fan-out characteristics of senders and receivers
of messages? What are some send-buffer and receive-buffer considerations
on each endpoint?

What is the difference between an address, an endpoint, a socket, and
a connection?

With a networked connection, or any other connection type that has fewer
guarantees on message delivery, what are some mitigation techniques for
robust message transfer?

These libraries are curated and designed to work well together
to build distributed applications and systems.

### Data Structures with JSON

There exist differences between statically-typed languages and dynamically-typed
languages.

Featherweight does not believe or adhere to a 'language' being dynamically- 
or statically-typed, but instead acknowledges that 'application domains' might
likely yield nicer solutions in one or the other type system.

For this reason, Featherweight developers are able to use the native
statically-typed LabVIEW type system for some problems, and use the FTW JSON
type system for others.

Considering data as it flows throughout a distributed system, if each node is
required to intimately be aware of all fields within composite types, each
node in the system will need to change as the data changes also.

Conversely, if each node in the system is only aware of the data that either
exists or does not exist within the object that flows through the node, it
is able to remain agnostic to the rest of the fields within the object. This
system is more robust against changes to data in the system.

JSON is chosen as one primary data exchange format today in FTW for a few reasons:

1) object interoperability with every other modern language
2) human-readability for debugging
3) past performance against other protocols (such as XML), and future predictions to continue to grow

{% include note.html type="info" title="Contrib" icon="info circle" body="In addition to JSON, FTW is considering additional interoperable serialization protocols, such as BSON and msgpack." %}

### Data Structures with SQLite

## FTW à la carte

FTW functions and libraries are designed to be independently accessible and integrated
à la carte into existing applications. It's an explicit design goal
of all FTW functionality to be independently- and arbitrarily-accessible,
without requiring you to deal with undesirable dependencies or awkward ties to
other parts of the framework.

That said, one good way to begin to use FTW is by slowly incorporating
immediately-useful features into your existing applications where you
already feel comfortable.

The FTW Core libraries do not rely on any external dependencies or
packages except for the C Runtime Engine (libc) and the LabVIEW Runtime Engine (lvrt).
For this reason, FTW is designed to run seamlessly on all general-purpose
targets, including Linux Real-Time, Windows 32-bit and 64-bit, and OS X
(but not FPGA, whose design patterns and idioms are substantially
different from high-level systems).

## Interop with non-LabVIEW Systems and Services

Featherweight provides

{% include note.html type="warning" text="" %}

## LabVIEW language bindings for C Libraries

The [Featherweight Kernel](https://github.com/featherweight/ftw-lib/) is an amalgamated
library of all C libraries used by Featherweight. This means that when
you use the LabVIEW libraries in your application, there will exist
just one shared library to distribute with your application.

* Windows: featherweight.dll
* LinuxRT: featherweight.x.x.x.so
* OS X: featherweight.dylib

The Featherweight Kernel is statically linked to the FTW APIs which use it,
meaning that developers building applications do not need to
explicitly include it in the build (NI Application Builder detects
the static link and includes it).

## Tradeoffs

Featherweight developers acknowledge tradeoffs exist and merits are
sometimes sometimes mutually exclusive.

Recognizing and characterizing tradeoffs, then choosing based on the
following guidelines and design decisions is what defines "ftw-esque" design.

We can tune knobs one way or another depending on what's important for the
task at hand.

Success in tuning these knobs is probably best determined by the measurable
amount of human delight that was created or human strife that was avoided.
Metrics such as "full-test coverage" or "no dependencies" or "extensive documentation"
in an of themselves are just facts of academic value. "Full-test coverage" could
come at the expense of ossification of suboptimal behaviors and interfaces of the
library, since re-writing the tests would be prohibitively expensive. "Extensive
documentation" could have come at the expense of simplifying the library to where
intuition

There exist balances in software development, where torquing the knob to 0 or 10
is 

* Code, features, tests, documentation are valuable assets, but they also represent
liabilities.

## Functional Programming vs. Object-Oriented Programming

Featherweight and ftw-esque applications extensively use key tenets
from both both Functional Programming (FP, not to be confused with
`Front Panel` in this context) and Obejct-Oriented Programming (OOP).

Briefly, FP states that the Function is the first-class citizen which
incidentally acts upon data, and OOP states that data is the first-class
citizen which may be manipulated and mutated only by the functions
explicitly trusted.

Turns out, both data and functions are important for developing applications,
so we utilize merits from both methodologies.

FTW libraries and ftw-esque applications:

* avoid mutable state at the library, application, and system layers
  in favor of transactional data (state travels atomically with messages
  between nodes), while ...
* ... wrapping virtual and real "things" as objects with coherent interfaces, while ...
* ... avoiding mutable state as fields in this object, where state is held by the "thing" itself, where the object is able to query this "thing" on-demand rather than attempting to solve the consensus and SSOT problems with distributed mutable state, while ...
* giving application developers using FTW the ability to change behavior of FTW objects through dependency injection and run-time polymorphism, while ...
* attempting to de-emphasize class inheritance, but instead providing entry points for defining Mixins or Traits of FTW objects, capable of acting upon arbitrary, dynamic datatypes.

## FTW vs. OpenG vs. MGI vs. GPower vs. vi.lib ...?

OpenG, MGI Toolkits, and GPower represent the most successful curated collections
of libraries in the LabVIEW community, and are widely acknowledged
for their long-proven usefulness, quality, availability, and support.

vi.lib, the shipping standard library for the LabVIEW Language, is 

FTW does not replace or compete with these collections of libraries. Rather,
many FTW users continue to use both in the same application.

FTW intentionally does not link to these libraries or any others for a few reasons:
* to avoid dependency collisions for end-users of all products
* to avoid unintentional dependencies beyond 

Instead, for a few functions where it would have been tempting to save
time as a FTW library developer and use existing functions, FTW has similar
methods, oftentimes tuned specifically for ftw-esque development.

## Differences

The LabVIEW community sometimes emphasizes a few ideals that ftw-esque
developers might 

* Keyboards lead to typos which lead to bugs. Mice lead to wiring which leads
to nirvana. Featherweight sometimes prefers typing to writing, where the
semantic-to-syntax ratio dictates. 
* Static types are bugs that don't happen; dynamic types are run-time
  errors waiting to happen. Perhaps, but one tradeoff is losing design patterns
  where nodes and functions remain agnostic to the entirety of data upon which
  they are acting, instead concerned only with the pieces of data of
  interest within the object.
* Dataflow == visible wires from function to function. Well... half true. That's
synchronous dataflow, where the flow of data also gates as execution control. The
generalized definition of "dataflow" is <i>d(data)/d(something)</i>, where <i>something</i>
might be time (for synchronous dataflow), and it could be asynchronous dataflow (e.g.,
message passing between nodes).