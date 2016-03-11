---
permalink: /docs/database-sqlite/
layout:    docs
title:     SQLite Database
menu:      SQLite Database
authors:
  - Jack R. Dunaway
editors:
  - placeholder
---

The FTW SQLite namespace provides an idiomatic binding between the SQLite
library and NI LabVIEW™.

## Database Persistence

SQLite provides two persistence models for databases: persistent (on-disk) and

## Insert and Fetch

Featherweight provides two type-adapting functions designed for inserting data
into and fetching data from the database.

These

{% include note.html type="security" title="Databinding" body="When inserting into and fetching from the database, binding data with these functions provides better security, accuracy, and performance compared to building the query as a string." %}

### FTW-SQLite-Insert.xnode

Featherweight provides a type-adapting function for inserting data called.

Despite the name `Insert`, this is useful for both `INSERT` and `UPDATE` SQL
commands where one or more rows will go into the database.

### FTW-SQlite-Fetch.xnode

Featherweight provides a type-adapting function for inserting data called
`FTW-SQlite-Insert.xnode`.
