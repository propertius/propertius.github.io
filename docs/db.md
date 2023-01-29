---
layout: default
title: Databases
nav_order: 6
---

# DB
{: .no_toc }

Random tips on databases.
{: .fs-6 .fw-300 }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Retrieve table for a given column name - Postgres

Sometimes you know the column name, but you do not know the table. Yes, it may happen :)

```sql
select table_name from information_schema.columns where column_name = 'foo';
```

## Flyway - migrate out of order

In the real world, migrations are not always generated in a perfect ascending order. For those cases, this line will ensure that migrations with an index higher than the ones already run are not ignored:

```shell
mvn -Dflyway.outOfOrder=true flyway:migrate
```

## List all users - Postgres

When you need to know which users are part of a particular database, issue this command within psql:

```shell
\du
```