---
permalink: /philosophy/
layout:    docs
title:     Design Philosophy
menu:      Design Philosophy
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

Featherweight is two things: a design philosophy,
and a framework implementing this philosophy in a
graphical programming language.


"Featherweight" is also a design principle for maximizing semantic-per-syntax
for application code, since lots of syntax is generally a liability more than an
asset.

## Code

No Code is Better than No Code.™

Said another way, there does not exist a bit of code
that is better that no code, given the same observable result.

Given two implementations of an application, where the
end-users of the application are unable to perceive or
detect differences in features, performance,

Software deliverables effectively have two sides. The outside
and the inside.

## FTW à la carte

Learning new things can be hard. Attempting to learn
too much at once sometimes doesn't work out well.

This is why one specific design decision for Featherweight
is to make sure that neat parts of FTW could start
to be used in your existing applications.

## FTW as a framework



## Dependencies



## Sides

Software has only two sides.

The inside, and the outside.

#### The Outside

An end-user, beneficiary, stakeholder or otherwise observer of
deployed software experiences its existence. Perhaps by inputting
information; and perhaps by being influenced by its output.

Software may interact with more than just humans, but <em>Featherweight
specifically seeks to characterize and optimize observable delight in
humans.</em>

#### The Inside

Developers see. Code. Processes. Design patterns. Deployment.


#### The Dividing Line


#### FTW has an Outside and an Inside

Featherweight is software for software developers. This gets a bit
meta, attempting to optimize for either its end-users or its
developers (where, a FTW developer is also an end-user).

Additionally, FTW is used to make software that likewise has an
inside and an outside. Choosing to use FTW in an application

This is a gross simplification of the many facets and nuanced
interactions between developers and end-users; yet, as developers
ourselves, we like such simple models in order to characterize
and debug.

## Codebase

Your codebase is both an asset and a liability.

## Maximal Semantic-per-Syntax

Syntax is an incidental complexity for conveying semantic,
and generally, making things happen.

The less syntax the better.

## Failure

Failure happens. Embrace this. Create robust systems with fail-safe
defaults that aggressively defend their ability to perform their job.

## Complexity

Complexity exists. Complexity is neither good nor bad; it's empirical.

Complication exists too, and that's probably not good.

Sometimes complexity can be eliminated. This might also require elimination
or consolidation of a feature or some semantic. That's usually a good tradeoff.

Eliminating -- or better, avoiding -- complication is usually good.

## NI LabVIEW™ Design Considerations

The Featherweight Framework for NI LabVIEW™ only incidentally
has some important parts written using the NI LabVIEW™ programming
language.

### LVOOP

There and back again.

### LVLIB

The overall value proposition is negative. The two main value propositions are
namespacing, then prerequisitely scoping within a namespace.

Other considerations, such as the ability to build an LVLIBP exist

Comically, the highest value proposition is the ability to create
a template icon for namespace members. Although unfortunate, this
loss is surmountable.

### XNodes

### Error Handling

This is a motley experience. Your mileage may vary. FTW adopts the following
error-generation and error-handling strategy:

#### Error Generation

Functions output by-value error structure values when they encounter unexpected
or error conditions.

Nominally, hexadecimal error codes are generated by FTW functions

#### Error Handling

### Graphical Programming

### Stability

The Featherweight Framework for NI LabVIEW™ is built upon NI LabVIEW™,
and therefore the Featherweight Framework for NI LabVIEW™ is only as stable
as NI LabVIEW™.

### Interoperability with C Calling Convention

The NI LabVIEW™ C foreign-function interface (FFI) could be way better.
But whatever; it hasn't changed since 2003. Subtitle: Featherweight,
brought to you by blood, sweat, and tears battling the LV C FFI.
