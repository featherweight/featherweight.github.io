---
permalink: /docs/
layout:    docs
title:     Welcome
menu:      Welcome
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

This site aims to be a comprehensive guide to Featherweight. We’ll cover
topics such as integrating useful bits of Featherweight into your existing
applications, diving deeper into applications and application components
written using Featherweight Reference Designs, and general system design
strategy and tactics applicable even outside of using the Featherweight
libraries.

## Helpful Hints

Throughout this guide there are a number of small-but-handy pieces of
information that can make using Featherweight easier, more interesting,
and less hazardous. Here’s what to look out for.

{% include note.html type="protip" title="Protip" body="Nuggets of wisdom, clever tips, and idiomatic spiciness to take Featherweight to the next level." %}
{% include note.html type="info" title="Info" body="Tidbits and minutiae to add clarity." %}
{% include note.html type="contribute" title="Contribute" body="The parts of Featherweight in a particularly mutable state should be used with caution in production, but they are also the pieces over which you can have the most influence." %}
{% include note.html type="warning" title="Heads up! FTW is weird here." body="Featherweight tries to not be opinionated, unintuitive, or klunky, but sometimes it just is. Guidance from Warnings helps make sure your application doesn't 'splode by falling into common pitfalls." %}
{% include note.html type="security" title="Security and Robustness Considerations" body="These notices are designed to point out issues that could affect the robustness or security of your application. Mission-critical application domains are urged to heed guidance here, and consult an expert when you're not sure." %}


If you come across anything along the way that we haven’t covered, or if you
know of a tip you think others would find handy, please [file an
issue]({{ site.repository }}/issues/new) and we’ll see about
including it in this guide.

## Highlights

### Revolutionary Messaging

Queues, events, notifiers, TCP networking, pipes, WebSockets - all configurable at runtime in a single API.

<a href="/concepts/sockets/">FTW Sockets &rarr;</a>

### Free. Open Source.

Permissive MIT License is business-friendly, even for proprietary and commercial applications

<a href="/licensing/">Benefits of permissive license &rarr;</a>

### Actor-oriented reference design

Reference designs for creating successful simple applications up to distributed systems

<a href="/concepts/actors/">FTW Actors &rarr;</a>

### Dynamic Typing

Natively a statically-typed language, FTW brings dynamic type containers to NI LabVIEW™.

<a href="/philosophy/">Containers &rarr;</a>

### Interoperable

Bridges the gap between developers in other programming languages using interfaces you're both comfortable with.

<a href="/what-is-featherweight/">Crossing language barriers &rarr;</a>

### Cross-platform

Supports all high-level targets for systems development, and seamlessly move modules from one target to another.

<a href="/what-is-featherweight/">Supported targets &rarr;</a>

### Write Less Code

Smaller diagrams means fewer bugs and less inertia to understanding other people's code.

<a href="/philosophy/">FTW Design Philosophy &rarr;</a>

### Rethinking Data Storage

Type-adapting native language binding maps wire types to SQLite, enabling powerful in-memory and persistent data structures.

<a href="/docs/ftw-database-sqlite/">FTW Sockets &rarr;</a>
