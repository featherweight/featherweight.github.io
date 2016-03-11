---
permalink: /docs/actor-job-scheduler/
layout:    docs
title:     Actor Instance Job Scheduler
menu:      Actor Job Scheduler
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

Each `FTW Actor Instance` owns one `FTW Job Scheduler`.

This `FTW Scheduler` is responsible for scheduling the order of execution of
jobs that the running `Actor Instance`.

Only the `Actor Instance` itself may add additional jobs to its own queue. No
other software module is able to directly or forcibly modify the scheduler
of an `Actor Instance`. Especially, an incoming request to any given Actor
Instance is not necessarily correlated to a job enqueued onto that Actor's
job schedule.

Arguably, if we imagine the Front Panel of the `Actor Instance`
as another "client" connected to "backend" Block Diagram,
this would be the only exception of an "external force" affecting
the `Scheduler` of the Actor Instance.

## What is a 'job'?
The `FTW Actor Job` defines one discrete procedure to be performed by the
`FTW Actor Instance`.

The Featherweight Actor Reference Design ships with a few framework-specific
jobs, and it also has a few templates that act as entrypoints for creating
your own actor-specific jobs.

## Job or Actor Instance Method?

A jobject has the following fields:

## Async Jobjects

A jobject may be scheduled in one of two ways: as Jobs enqueued
into Job Queues the Scheduler Job Queue, as an asynchronous jobject
that fulfills a request from an Actor Connector.

## Jobject Examples

A trivial jobject will decompose into a single job handler placed
into one of the priority job queues by the `FTW Actor Scheduler`.

## Compared to the JKI State Machine

The reference design for Featherweight Actor Instances is based upon the
JKI State Machine.

The authors of this document acknowledge its long-standing success stemming
from thoughtful design.

If you have found success and feel comfortable with the JKI State Machine, it's
likely that FTW Actor design of job schedules will translate swimmingly.

## Job Sequences

By default, each time around the outer loop in the [Featherweight Actor Reference Design]()
`Actor Instance`, the framework checks if an error exists that was shifted
from the previous iteration. On error, the framework preemptively schedules
the `FTW Job: Handle Error` job.

When using  and creating
multiple Job Handlers (i.e., more cases in the case structure), the application domain
sometimes requires that multiple

## How do I "Clear All Jobs" or "Empty Schedule"?

This is neither recommended nor enabled by design.

The desire for such a feature almost always rooted in a suboptimal design.

## How do I schedule a job to happen after pending jobs?

This is neither recommended nor enabled by design.

The desire for such a feature almost always rooted in a suboptimal design;
enqueueing a new job (or job sequence) will always preempt pending jobs.

The reason that newly-enqueued jobs are not able to take a lower priority than
existing pending jobs is because, paradoxically, the Actor Instance is strongly
recommended against introspecting its own future schedule. (Further, no method
exists in FTW enabling a "peek" into or even modify queued jobs)

## Shutting Down

Calling the `FTW-Actor-Instance-BeginShutdownSequence` method will preemptively
schedule the shutdown sequence of the actor.

## Job Prioritization

A `FTW Scheduler` has precisely one job priority applied to newly-enqueued
jobs: **do it now**.

A common concern: "What if a message comes in while a sequence of jobs is
underway, but I do not want that message to interrupt the sequence?"

The simple answer: do not schedule the `FTW-Job-HandleIncomingMessage` job
during the sequence!

But, "What if I do want it to interrupt the sequence of jobs?"

Conversely, schedule the `FTW-Job-HandleIncomingMessage` job interleaved between
each location the job sequence could be interrupted (e.g., cancelling a
a long-running sequence).

## Scheduling Strategies

Currently, the only scheduling strategy for pending jobs of an Actor Instance is
sequential LIFO.

This is by design, since the Actor Instance is the primary atom of concurrency
in Featherweight.

For tasks that need to happen concurrently and/or in parallel, these tasks are
perhaps better divided per-actor, since actors naturally run in parallel and
concurrently with one another.

### Standard Sequencing FIFO

The default strategy for choosing execution order of jobs is
a last-in first-out (LIFO) queue.

### Preemptive FIFO



##
