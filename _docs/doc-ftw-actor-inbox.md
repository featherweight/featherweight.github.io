---
permalink: /docs/actor-inbox/
layout:    docs
title:     Actor Inbox
menu:      Actor Inbox
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

A `FTW Actor Inbox` receives messages from one or
more locally-bound endpoints, then delivers them to the
owning `FTW Actor Instance` based on the priority schedule
configured in the inbox.

A `FTW Actor Inbox` may be thought of as a booking agent.
Messages received into an actor's inbox are not routed immediately
to the process for handling; instead, the inbox is capable
of filtering, sorting, rejecting the message and returning
a failure to the sender (without bothering the Actor Instance),
generating an automated response (such as PONGing a PING),
and batching incoming requests of the same type to be delivered
as an array on a set schedule.

## Actor Instance Configuration

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>Field</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><p><code>InboxAddress</code></p></td>
      <td><p>The relative address of the inbox with respect to the Actor Context.</p></td>
    </tr>
    <tr>
      <td><p><code>InboxPriority</code></p></td>
      <td><p>An integer value from [0,10]</p></td>
    </tr>
    <tr>
      <td><p><code>content</code></p></td>
      <td><p>

        In layout files, the rendered content of the Post or Page being wrapped.
        Not defined in Post or Page files.

      </p></td>
    </tr>
    <tr>
      <td><p><code>paginator</code></p></td>
      <td><p>

        When the <code>paginate</code> configuration option is set, this
        variable becomes available for use. See <a
        href="../pagination/">Pagination</a> for details.

      </p></td>
    </tr>
  </tbody>
</table>
</div>

### Example
{% highlight json %}
{
  "InboxAddress": "/stage/motor/x-axis",
  "Priority": 5
}
{% endhighlight %}


## Centrality of Data

## Actors are Citizens
A good analogy of for an Actor Instance is to consider it a citizen
of a society (where, society is an analogy to `Actor Context`).

This society has limited resources (an Actor Context has finite RAM, CPU, etc...),
and for this reason the Actor Instance

## Centrality of Health
An Actor Instance is always expected to keep itself "healthy", sometimes
at the expense of fulfilling the requests of other Actors. This includes
per

## Assumed Statelessness between Actors

One important assumption to maintain is that all communication between
all Actors assumes no previous state of peer.

This means that even though a local endpoint may be aware that it is sending
messages in succession, it should not assume that the remote endpoint
is neither in an assumed state for subsequent messages nor even receiving
the messages in the same order as being sent.

For those of us who 

## Cost of Failure vs Reasonable Expections

The principles of Actor-Oriented design are not necessarily absolute rules.

For instance, it's often convenient to forget the "at most once" and
assume that messages sent will be reliably received.

The tradeoff and balance of this concession is based upon reasonable
expectations of reliability far exceed the cost of failure for infrequent
times when the expectation is not met.

A good example of a reasonable expectation of success and low cost of
failure is a touch-sensitive keypad on a microwave oven. While setting the time,
most of the times pushing the buttons works the first time, and in the event of failure,
the operator will simply press again, or perhaps clearing and correcting
an incorrect button. A less clear-cut scenario is using that same touchpad
to stop a microwave that is running as soup boils over. For this reason,
on most microwaves, there exists a much larger hardware button that stops operation
of the microwave that's easier to lunge toward (and more ergonomically suited
for lunging, with a contact area of several fingers or a fist instead of just
a fingertip!) Would it be cost-effective for the microwave manufacturer
to optimize success rate of the keypad from 99% to 99.99%? Perhaps not, given
the cost of failure is insignificant and easily-rectified. (Also, would the
"better" solution have been as easy to wipe off and clean?)

If codified, perhaps consider this heuristic: as expectation of success becomes
more and more probable, it's OK to tune the "paranoid" knob lower; as cost
of failure increases, tune the "paranoid" knob higher. "Paranoid", meaning additional
procedure and requisite syntax to develop and maintain as a remedy for
or reaction to forseen failure modes.

### Design patterns and idioms for mitigating failure

#### Publishing level instead of level-change events
Some design patterns for mitigating failure include unconditionally publishing
state (level detection) versus expecting to catch a single message (level-change
detection). Since this could connote aliasing and missing state changes, when it's
critical to catch such short "pulses", a local detector on the publishing
endpoint would publish such occurences as a separate channel (e.g., in addition
to published "OverVoltage" as a boolean, "OverVoltageOccurrences" could be
a numeric counter. In the event that the OverVoltage condition was set and then
cleared between two publish periods, the receiver would receive two subsequent
messages stating that "OverVoltage" is false except that "OverVoltageOccurences"
has incremented by one.

{ include note.html type="notice" title="Remember" text="Continually publishing messages is one method of mitigating lost message, but even (and perhaps, especially these since bandwidth is increased) these messages may be lost." }

## Tips on Dividing Applications into Actors

Let's create for ourselves a scenario for an application and consider
how we might divide application requirements into Actors Instances.

Consider this application requires:

* one voltage channel
* one current channel
* one output relay
* one algorithm and visualization for voltmeter data
* one algorithm and visualization for ammeter data
* one algorithm and visualization for voltmeter+ammeter data

One trivial manner of segmenting actors is to consider "one application;
one actor!"

Another trivial solution is "six things, six actors".

Or perhaps, we divide the hardware into one actor, put the the UI
into another actor, and defer the decision of where to do the calculations
since it seems easy enough to move

Are these options all valid? Yes! Are they optimal? Perhaps; perhaps no.

To begin to consider other compositions, we need to start considering
additional things. In the spirit of this example, let's tailor some
questions we might ask ourselves:

#### Are the three physical channels on the same bus?

If the three channels (2 input, 1 output) are on separate busses
(e.g., separate instruments with separate connections to that instrument),
likely they can reasonably be separated into two actor instances if desired.

If they are on the same bus, they very likely must exist within the same
actor instance, because even though the channels may be physically independent,
the bus acts as a shared resource between the independent channels. If we were to
place control into separate actors, we might encounter collisions over this
shared resource. For example, which actor initializes/deinitializes the device?
What happens physically when the bus receives two simultaneous commands - does
the protocol return an error for one, or queue one after the other? Regardless
the specific workaround for such hard/specific/discretionary questions, it might
have been easier to avoid them altogether.

In this manner,
we might visualize the instrument bus as an actor system itself.

The "Actor Connector" to this system is the hardware bus connection which either
continually publishes measurement data, or has a Request/Reply semantic
implementing "Get Voltage" and "Get Current", or perhaps "Get Measurement" that
returns a structure of both measurements.

{ include note.html type="notice" title="Cool tip (need sunglasses glyph)" text="Instruments with remote control protocols map exceptionally well to Actor Systems. They typically maintain their own health (e.g., a 10W power supply might return an error if commanded to 1 megawatt), define a published interface" }

#### Do the two physical channels have an implicit shared resource - time?

If the measurements must be timed with respect to the other, this timing
requirement acts as an oft-overlooked 

## Public vs. Private vs. Published Interface

The interface of an Actor is a bit like and a bit unlike that of a
traditional object-oriented class whose methods dispatch on the call stack
of the caller.

The traditional OO API has:

* public methods/properties/fields: any code may dispatch and use
* protected methods/properties/fields: only descendent classes may dispatch;
  non-descendents that attempt to use will throw a compiler error about scope
* private methods/properties/fields: only methods of the class itself can
  link to or dispatch these; even descendent classes will throw an error
  
An Actor, on the other hand, has:

* No "public" methods/properties/fields
* Protected methods/properties/fields: may be used by the actor instance,
  or children of the actor instance
* Published requests ("methods"): the list of "methods", roughly analogous
  to remote procedure calls (RPC), that the actor will respond to. The "published"
  interface 

### Published Interface

This is the list of messages

{ include note.html type="notice" title="Note" text="The Featherweight Framework defines a few framework-level messages" }

### Published Data
An actor is able to broadcast arbitrary data to remote endpoint(s) who
choose to connect to the Actor's publisher endpoint(s).

Each actor instance chooses a rate at which it desires to publish. This could be
periodic (e.g., every 100msec), or sporadic (e.g., notification of an event).

Each actor may define [0, N) publishers on which it publishes arbitrary
data to each channel.

## Inheritance of Actor Instances

The Actor Reference Design in Featherweight allows inheritance. The simplest
example is how application specific Actors you write will likely inherit from
`FTW-Actor.lvclass`.

{ include note.html type="warning" title="Heads up!" text="It's possible to create your own reference designs that compose and wrap core FTW-ActorInstance functions, but this is not necessarily recommended. " }
