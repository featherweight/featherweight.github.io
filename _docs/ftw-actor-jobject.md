---
layout: docs
title: Actor Jobject
permalink: /docs/ftw-actor-jobject/
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

The `FTW Actor Jobject` defines a procedure or sequence of procedures to be performed by the
`FTW Actor Instance`.

`Jobject` is a portmanteau of 'job' and 'object' which is interpreted
by the scheduler 

## Jobject Decomposition

A jobject has the following fields:

## Async Jobjects

A jobject may be scheduled in one of two ways: as Jobs enqueued
into Job Queues the Scheduler Job Queue, as an asynchronous jobject
that fulfills a request from an Actor Connector. 

## Jobject Examples

A trivial jobject will decompose into a single job handler placed
into one of the priority job queues by the `FTW Actor Scheduler`.

