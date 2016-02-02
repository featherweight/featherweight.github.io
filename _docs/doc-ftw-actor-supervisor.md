---
permalink: /docs/actor-supervisor/
layout:    docs
title:     Actor Supervisor
menu:      Actor Supervisor
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

The `FTW Actor Context` is a conceptual bounded region
of the unbounded ether within which actors live and die.

The `FTW Actor Context` additionally has:

* one `FTW Actor Logger`, which acts as the default logger for
  all actors within the context.
* the ability to manage actors through a web interface
* one LabVIEW Application Reference **
* the ability to act as a bootstrapper to construct/destroy the Featherweight kernel library
* the ability to act as a bootstrapper for applications written in FTW, including Splash Screen
* context GUID, known only to the context and its owned actors
* context address


** Note: it is undecided whether Featherweight will enable spawning
of Actors into remote LabVIEW Application References, since this connotes
pre-knowledge

** Note: it is undecided whether Featherweight Actors will continue to have individual inbox addresses, or whether they will be addressed relative to their Context. Right now, I'm 80%+ in favor of relative addressing, meaning there would only need to exist one socket for external communication (internally, actors could address each other directly based on an inproc socket as context


## Actor Ownership

The `FTW Actor Context` acts as a walled garden of an arbitrary
grouping of `FTW Actor Instances` within an application. An application
may have one or

The Actor Logger logs events and exceptions within
an [Actor Context](/docs/ftw-actor-context/).

It provides an [HTTP interface](#http-client-interface)
for viewing these logs


## HTTP Client Interface

The Logger Interface enables you to view and sort through
all events and exceptions that have occured

By default, the logger is enabled only for viewing
on the local machine, but it may be enabled to be accessible
via a closed intranet.

{ include note.html type="warning" text="Even though it is possible to expose the HTTP Client Interface publicly on the internet, this is strongly discouraged. One reasonably-secure alternative is VPN into a private intranet, but even the security considerations here should be thoroughly investigated." }

{ include note.html type="contrib" text="We need to get https:// and wss:// into Featherweight. In the meantime, it is strongly discouraged enabling the HTTP Client Interface for access through the internet." }


## Pruning and Retention Policy

Each logger instance has a configurable data pruning and
data retention policy.

By default, log entries will be automatically pruned based
on number of records.


{ include note.html type="warning" text="Changing the local system time on your computer may trigger " }

{ include note.html type="warning" text="The logging schema may change without warning when upgrading Featherweight, including dropping existing tables. Do not rely upon this the persistence or durability of this log or its structure for business-critical purposes." }

{ include note.html type="warning" text="The pruning policy removes data permanently. The FTW Logger is intended for system troubleshooting, and should not be used for mission-critical data." }

## Histogram

Each log entry
