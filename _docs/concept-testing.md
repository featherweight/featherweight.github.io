---
permalink: /testing/
layout:    docs
title:     Testing
menu:      Testing
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

Featherweight ships with a lightweight testing framework
called Featherweight Test.

This test runner framework is designed specially designed for rigorous
unit tests and integration tests of Featherweight for all
platforms.

Featherweight tests double as example usage of all framework
abilities.

{ include note.html type="protip" text="If you are new to Featherweight, start by perusing the tests. They double as examples, contain clarifying commentary on behavior, and illustrate framework abilities." }

## Running the Tests from the IDE

After [cloning the repository](/download/) or [downloading a
snapshot](/download/), navigate to the following directory:

`ftw/tests/`

From here, open `test.vi`

## Running Tests from the Command Line

The test runner is built as an executable application for each
supported platform, including static links to each of the tests
for that platform.

It is designed especially for [FTW Kernel](/concepts/kernel/) development,
such that automated tests from each of the C libraries may
be run as part of the `make check` process


## Running Tests as part of your Application

The test runner may be statically compiled into your
application in order to perform tests at run-time.

Additionally, 

{ include note.html type="warning" text="Featherweight Test is not intended to be a full-featured test runner." }

## Interpreting the Test Report

Featherweight Test generates a 

## Writing Decent Tests

Just like your codebase, tests are both an asset and a
liability. 

Not enough testing can hurt you. Too much testing can hurt you.

Featherweight specifically does not aim for or promote
"X% test coverage".

Rather, Featherweight aims for this:

**enough tests to provide reasonable confidence a human
does not look at FTW or something created with FTW and
think "WTF".**