---
permalink: /docs/ftw-actor-scheduler/
layout:    docs
title:     Actor Instance Job Scheduler
menu:      Actor Scheduler
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

Each `FTW Actor Instance` owns one `FTW Job Scheduler`.

This `FTW Scheduler` is responsible for scheduling the order of
execution of jobs that the running `Actor Instance`.

Only the `Actor Instance` itself No other software module is able to directly or forcibly modify the scheduler
of an `Actor Instance`

Arguably, if we imagine the Front Panel of the `Actor Instance`
as another "client" connected to "backend" Block Diagram,
this would be the only exception of an "external force" affecting
the `Scheduler` of the Actor Instance.

## Job Sequences

By default, each time around the outer loop in the [Featherweight Actor Reference Design]()
`Actor Instance`, the framework checks if an error exists that was shifted
from the previous iteration. On error, the framework preemptively schedules
the `FTW Job: Handle Error` job.

When using  and creating
multiple Job Handlers (i.e., more cases in the case structure), the application domain
sometimes requires that multiple 

## How do I "Clear All Jobs" or "Empty Schedule"?

This is not allowed by design.

There does exist

## Shutting Down

Calling the `FTW-Actor-Instance-BeginShutdownSequence` method will preemptively schedule
the shutdown sequence of the actor.

## Job Prioritization

A `FTW Scheduler` implements three `Job Queues` 

## Scheduling Strategies

### Standard Sequencing FIFO

The default strategy for choosing execution order of jobs is
a first-in first-out (FIFO) queue

### Preemptive FIFO



## 