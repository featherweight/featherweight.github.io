---
layout: docs
title: Actor Logger
permalink: /docs/ftw-actor-logger/
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

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

{% include note.html type="warning" text="Even though it is possible to expose the HTTP Client Interface publicly on the internet, this is strongly discouraged. One reasonably-secure alternative is VPN into a private intranet, but even the security considerations here should be thoroughly investigated." %}

{% include note.html type="contrib" text="We need to get https:// and wss:// into Featherweight. In the meantime, it is strongly discouraged enabling the HTTP Client Interface for access through the internet." %}


## Pruning and Retention Policy

Each logger instance has a configurable data pruning and
data retention policy.

By default, log entries will be automatically pruned based
on number of records.


{% include note.html type="warning" text="Changing the local system time on your computer may trigger " %}

{% include note.html type="warning" text="The logging schema may change without warning when upgrading Featherweight, including dropping existing tables. Do not rely upon this the persistence or durability of this log or its structure for business-critical purposes." %}

{% include note.html type="warning" text="The pruning policy removes data permanently. The FTW Logger is intended for system troubleshooting, and should not be used for mission-critical data." %}

## Histogram

Each log entry 