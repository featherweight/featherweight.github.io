---
layout: docs
title: Actor or Object
permalink: /concepts/actor-or-object/
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

It can be difficult sometimes to know whether it makes more
sense to create a by-reference object to represent a component
in the system, or to create an actor.

For instance, consider a voltmeter instrument. Should this
instrument be represented by a by-val object callable as a
regular API on the call stack of the caller?

Should the voltmeter become a FTW Actor with its full abilities,
such as publishing voltage, maintaining health of bus connection
with the instrument, and providing a remoteable API via messaging?

Or should the lowest-level voltmeter API (say, direct RS-232 or
TCP communication with SCPI commands) be part of a collection of
other similar low level commands to additional instruments, all
aggregated in one actor to appear to the outside world as a single
aggregate instrument?
