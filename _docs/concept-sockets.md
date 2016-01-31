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

<div class="mobile-side-scroller">
<table>
  <thead>
    <tr>
      <th>Scheme</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><p><code>tcp://</code></p></td>
      <td><p>
      
        Actors 
      
      </p></td>
    </tr>
    <tr>
      <td><p><code>ws://</code></p></td>
      <td><p>
      
        Ruleset that governs how the actor reacts to Ask and Tell requests from remote actors. Each inbox in the array includes address where it listens for requests, its priority with respect to other inboxes, and message handling semantics for different message types.
      </p></td>
    </tr>
    <tr>
      <td><p><code>ipc://</code></p></td>
      <td><p>

        Inter-process communication using OS-level messaging facilities (nominally, pipes) for inter-application communication on the same compute target.

      </p></td>
    </tr>
    <tr>
      <td><p><code>inproc://</code></p></td>
      <td><p>

        In-process transactional memory for communication within the same application space and execution context. This is nominally the fastest, but also the least flexible with regard to location transparency.

      </p></td>
    </tr>
  </tbody>
</table>
</div>

{ include note.html type="protip" text="Consider " }
