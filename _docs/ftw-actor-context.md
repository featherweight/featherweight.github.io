---
layout: docs
title: Actor Context
permalink: /docs/ftw-actor-context/
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