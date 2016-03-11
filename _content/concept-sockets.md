---
permalink: /concepts/sockets/
layout:    docs
title:     Socket Concepts
menu:      Socket Concepts
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

As a framework for distributed system design, Featherweight
is equipped with the best messaging framework available
today for LabVIEW.

## FTW Sockets

The APIs used for messaging in Featherweight are called `FTW Sockets`.

FTW Actors own individual sockets used to send messages to one another.

FTW Actors use socket types and wire-level serialization protocols
that make them readily-interoperable with other actors (and things
that appear to be actors) in other languages and execution systems.

### Message Transport Schemes

Each FTW Socket topology offers four types of

<table class="ui celled table">
  <thead>
    <tr>
      <th>Scheme</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>tcp://</code></td>
      <td>Actors</td>
    </tr>
    <tr>
      <td><code>ws://</code></td>
      <td>Ruleset that governs how the actor reacts to Ask and Tell requests from remote actors. Each inbox in the array includes address where it listens for requests, its priority with respect to other inboxes, and message handling semantics for different message types.</td>
    </tr>
    <tr>
      <td><code>ipc://</code></td>
      <td>Inter-process communication using OS-level messaging facilities (nominally, pipes) for inter-application communication on the same compute target.</td>
    </tr>
    <tr>
      <td><code>inproc://</code></td>
      <td>In-process transactional memory for communication within the same application space and execution context. This is nominally the fastest, but also the least flexible with regard to location transparency.</td>
    </tr>
  </tbody>
</table>

{% include note.html type="protip" body="Consider " %}
