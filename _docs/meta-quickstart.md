---
permalink: /quickstart/
layout:    docs
title:     Quick-start guide
menu:      Quick-start guide
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

If you're new to Featherweight, it's recommended to first skim
through the documentation (especially the synopses of each namespace).

Next, it's worthwhile to begin


{% include note.html type="warning" title="Easy there" body="Perhaps avoid trying to refactor your 20k VI distributed system as your first project learning Featherweight!" %}

## Installation

Featherweight is not released as a package. It intentionally does
not install palettes, examples, libraries or otherwise into your
development environment.

Instead, FTW explicitly avoids existing outside the context of your
application repository, because everything that is
not in source code control by definition is out of control.

For this reason, the recommended method of using FTW within
an application is by forking the Featherweight repository,
then including the fork as a submodule within your application
repository.

## Using Git for your application repo

If your application repository is within Git, the simplest
method for using Featherweight in the application is to
have a Featherweight SubModule.

1. **Fork Featherweight:**
   This may be a private repository (i.e.,
   only you and those to whom you give permission may see and
   modify). By forking, you ensure that changes made to the
   Featherweight Master may be easily merged into or pulled
   if desired.
2. **Create Submodule:**
   - Git Users: this is called a `submodule`
   - SVN Users: this is called a `subrepository`
3. **Add to LVProj:**
   It's recommended to add only the FTW Source directory
   to your project so that examples and tests are not linked.

{% include note.html type="protip" title="Looking for git hosting?" body="(<i class='fa fa-github-square'></i>GitHub)[https://github.com/pricing] is a particularly excellent host. They offer hosted solutions for private repositories, self-hosted solutions, and integrated issue tracking. (Featherweight)[https://github.com/featherweight/featherweight], [this website](https://github.com/featherweight/featherweight.io), and the [Featherweight Kernel](https://github.com/featherweight/ftw-kernel) are all hosted on GitHub." %}

## Rationale for using SCC rather than a package manager

Packaging a library connotes a high degree of ossification. One would favor
a packaged library where this is desirable.

In reality, when creating applications, Featherweight authors
have found it useful to be able to modify framework code when
it makes sense.

Rigidity is specifically traded here for the flexibility to move
forward with the application, rather than awkward workarounds
of a fixed binary interface to the library.

Over time, patterns develop, and the same modifications are
made from project to project. As a rule of thumb, once these
patterns emerge across three or more projects, those modifications
are considered for upstreaming into the Featherweight root
repository.

By keeping Featherweight as a submodule of the application
repository, all such modifications are safely stored and
documented, making post-mortem of evaluating such changes
straightforward.

One day, it may be desirable to officially value hardening
of the Featherweight ABI and API by releasing versioned
packages, but for now submodules offer a substantially higher
value proposition.
