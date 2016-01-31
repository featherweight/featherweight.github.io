---
permalink: /concepts/messaging/
layout:    docs
title:     Messaging Concepts
menu:      Messaging Concepts
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

As a framework for distributed system design, Featherweight
is equipped with the best messaging framework available
today for LabVIEW.

## FTW Messaging Dictionary

####message
a finite piece of data that contains at least
the presence of a control signal, and often additional data
we'll call the payload

####message payload
data carried along with the message

####transactional data
related to message payload, this is the set
of data associated 

####statelessness
notion that other nodes in a network do not retain
memory or awareness of previous messages sent.

####socket
a conceptual hub into which messages 

####node
a physical (or virtual) entity that exists within a context

####network
the collection of all nodes

####system
a coherent subset of nodes on a network that interact
with one another to form an application or related set of applications

####application
the coherent set of nodes that interact with
one another to

####context
the physical (or virtual) space in which a finite,
bounded group of references exists.

####ether
the conceptual time and space in which all contexts (and
therefore all nodes) and all messages exist

####unbounded nondeterminism
asdf

####network congestion
asdf

####backpressure
ability of a sending endpoint to synchronously sense
that the recipient endpoint is currently unable to receive additional
messages because that remote endpoint's receive buffer is full.

####temporal locality
the relationship of entities with
respect to time. Entities are said to "temporally coexist"
for the period of time their lifetimes overlap

####lifetime
the period of time from which an entity exists to when
it is destroyed or self-destructs

####spatial locality
the relationship of entities
with respect to physical (or virtual) context location.
Entities are said to "spatially coexist" if they reside
within the same context.

####endpoint
the conceptual object that exists within a socket to
which and from which messages flow.

####peer
another socket, local or remote

####address
a string representing a UID within a context at which
an endpoint resides. No two endpoints may share the same address
within

####URI
Uniform Resource Identifier. A codified manner in which to
represent an address as per RFC xxxx. 

####connection
the presence of a channel between one or more nodes

####discovery
the process by which endpoints become aware of addresses
of other endpoints. There exists only four methods of discovery:
* receiving addresses synchronously at the spawning of one's lifetime
* asking another node (a directory service) about the address of other nodes
* being told addresses by another node
* creating new endpoints (or nodes that are known to construct endpoints),
  thus implicitly knowing the address before it exists

####directory service
a central node that implements the ability be
aware of a set of addresses for other nodes/services

####centralized message broker
an intermediate

####brokerless messaging
ability of peer nodes to send and receive messages directly
without going through a single centralized broker

####channel
asdf

####connector
asdf

####pipe
asdf

####connect
process by which an endpoint establishes

####secure connection
within the context of Featherweight, usage of
Transport Layer Security (TLS, [link to spec]) prior to establishing
connection

####bind
process by which an endpoint declares itself as "listening"
on a local address (or set of addresses). Once listening for incoming
connection requests (from a remote

####location agnostic
the ability to converse with a peer with minimal or no impact
from the physical or virtual location of the peer. A software
module designed such that it may reasonably be deployed on one
target or another (including, cross-platform and cross-architecture)
is said to be "location agnostic", where peers are required to
do no more than update an address.

####send
asdf

####receive
asdf

####command
a command is a type of message that does not exist in
actor-oriented design! "Command" connotes the ability to control, and
an actor never is able to explicitly control 

####request
a message sent to an endpoint in expectation of a response.
A request/response pair 

####ask
a special send/recv semantic where a request is sent to a peer
and a response is expected in return.

####tell
to send a message with no expectation of a response.

####poison pill
a message type (specifically, a request) that asks the
recipient node to destroy itself.

####respond
(synonymous with 'reply', the verb) a message sent to fulfill
a request transaction

####response
(synonymous with 'reply', the noun)

####timeout
asdf

####retry
process of resending a message that is lost (e.g., no confirmation
that the message was received by the remote endpoint)

####send buffer
space allocated at an endpoint capable of sending messages.

####receive buffer
space allocated at an endpoint capable of receiving messages.

####message transport
abbreviated "transport", this is the physical and
virtual infrastructure used to actually perform the delivery of a
message from one endpoint to another. A message transport thus may have
many components, including send/recv buffers, intermediate brokers, transport
headers on a wire-level protocol, and so forth.
protocol, 

####fan out
ability of a socket to send messages to more than one connected
endpoint. Nominally, the same message is sent to all connected sockets.

####fan in
ability of a socket to receive messages from more than one connected
endpoint.

####message queue
asdf

####bandwidth
asdf

####throughput
asdf

####lossless
asdf

####lossy
asdf

####port
asdf

####message priority
the priority of a message with respect to other messages
in the same message queue. [This should not exist!](#priority)

####head of line blocking
condition where a message resides within a portion
of the message queue where it cannot be rearranged with respect to other
messages resulting in a strict FIFO semantic.

####socket topology
the semantic applied to a socket that defines its
send/recv behavior and abilities

####publisher socket
a socket type that sends messages on a channel and remains
unaware of the existence of [0, N) subscriber sockets connected to the channel.
Conceptually, messages flow as a stream and fan out to all subscribers, where
the loss of messages is tolerated.

####subscriber socket
a socket type capable of subscribing to a publisher
(or multiple unique publishers) in order to receive messages streamed from the
publisher. A subscriber should be able to tolerate lossiness.

####producer socket
a socket type that pushes messages into a message queue and
remains unaware of the existence of [0, N) consumer sockets consuming
the queue and [0, N) additional peer producer sockets pushing into the
same queue.

####consumer socket
a socket type that pulls messages from a message queue,
unaware of the existence of [0, N) producer sockets pushing
into the queue.

####client (request) socket
asdf

####server (reply) socket
asdf

####topic
conceptual ability of a publisher socket to produce independent
channels to which subscriber sockets can conditionally subscribe. This is
an additional 

## Priority and Urgency

Different messages have different semantic priorities.

Take the analogy of vehicles traveling on the same roadway.

A car with a family leisurely headed to an ice cream parlor has
less urgency and less priority than an ambulance rushing to the
hospital.

Here, the vehicle represents the message, and the roadway represents
the message transport (recall, a #message-transport
