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

One concrete example might be the choice between CSV versus JSON
or SQLite

### Legacy versus future-proof

There exist plenty of useful programming protocols that may be useful
and even widespread, yet not strategic for adoption because of the
future trajectory of that protocol.

### Too hip?

If a particular library is only used by the cool cats, but no
