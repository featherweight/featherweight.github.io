---
permalink: /governance/
layout:    docs
title:     Governance
menu:      Governance
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

Although the Featherweight project is free and open source, it
is designed and developed as a professional product.

As such, a level of quality control is expected of all contributions

The Featherweight libraries and brand currently employ the BDFL
governance model run by Jack R. Dunaway.

## Are all contributions accepted?

No.

The first filter for acceptance of a feature is product strategy.
A non-exhaustive list of considerations include:

### Is the contribution _generally_ useful, usable, and desirable?

As an example, numeric addition and subtraction are pretty generally
useful and desirable. Contrasted, some esoteric mathematical transform
or function may be specifically useful, but not for a broad userbase.

For this reason, usefulness alone is not debated nor considered for inclusion.

Such useful functions should be kept in separate repositories, and at
some point in the future the core Featherweight repository might aggregate
a list of such useful repositories.

### Might the feature be useful, yet promote abuse?

One concrete example might be the choice of INI over JSON as a configuration
format, or CSV over SQLite for a persistence format. INI and CSV are specific
examples of widespread (and ostensibly, desirable) protocols that don't serve
as well as better protocols, and therefore will not be included into Featherweight.

### Legacy versus future-proof

There exist plenty of useful programming protocols that may be useful
and even widespread, yet not strategic for adoption because of the
future trajectory of that protocol.

### Too hip?

The opposite of legacy, if a particular library or protocol or design pattern is
only used by the cool kids, but has not yet proven itself over the test of time,
or especially if it appears a competitor will be the market winner, we'll sit on
the decision for a while.

Once a feature is in, it's hard to take out, so it'd best reside as a separate
library in the meantime.

One notable example is choosing a binary serialization protocol, such as BSON,
protobuf, or msgpack. Even having watched these protocols since Featherweight had
just hatched in 2012, now at the time of writing years later, it remains unclear
if one should be chosen for inclusion into Featherweight. (Sidenote: why not all?
Since Featherweight strives to provide a curated set of orthogonal tools, where
inclusion of multiple similar functionalities is a non-goal.) Additionally, their
value-add over JSON remains arguable across the spectrum of considerations.
