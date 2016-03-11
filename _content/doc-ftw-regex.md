---
permalink: /docs/regex/
layout:    docs
title:     Regular Expressions
menu:      Regex
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

Regular Expressions form the basis of declarative string manipulation in
Featherweight.

Ideally, structure of stringly-typed data is in the form of a well-defined
serialization protocol such as JSON or XML or HTML, but this is not oftentimes
the case.

And even when composite data is framed with such protocols, the values
themselves may be unstructured.

One such source of unstructured, free-form information is data entry
from a human, especially when using natural language.

## Using Regular Expressions to constrain Serial protocols

One notable example for regular expressions is to precisely and comprehensively
parse serial protocols.

Connections to hardware over legacy buses such as RS-232 or RS-485 often are
accompanied with protocols notorious for low confidence of data integrity. One
example would be a noisy/flaky bus with a small checksum, such as CRC16 (or worse,
no checksum).

Buses and higher-layer protocols built on top of TCP/IP are typically immune to
such corruption at the wire-level (since this is built into the TCP layer), but
other buses such as RS-232 or RS-485 are susceptible to line noise

As such, constraining the bytes as tightly as possible positively correlates to
the rejection of transmissions suspected to be corrupt.

Additionally, tight constraints

### RS-232 example

### Accepting multiple versions of a protocol
