# awesome-innovative-databases
A curated list of potentially game-changing database systems, maintained by [Vettabase](https://vettabase.com).

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) Inspired by the `awesome-*` trend on GitHub.

## Table of Contents

* [Active Projects](#active-projects)
* [Cemetary of Great Ideas](#cemetery-of-great-ideas)
* [Projects Information](#projects-information)
* [About](#about-this-project)

## Active Projects

* [Dolt](#dolt) - Git for relational data, compatible with MySQL.
* [immudb](#immudb) - Immutable, cryptographically verified, multi-model database.
* [TypeDB](#typedb) - Allows to define complex types and ontologies.

## Cemetery of Great Ideas

This is a very sad place. But some necromancer might decide to bring one of these projects back, as long as they are [Open Source](https://opensource.org/osd) / [Free Software](https://www.gnu.org/philosophy/free-sw.en.html).

We bury a project in this cemetary if the most recent commit or public release is at least 2 years old, or if the project was officially discontinued.

* [ActorDB](#actordb) - A sharded database for the actor model.
* [NoSQL](#nosql) - A relational database that replaces SQL with a set of simple command-line tools.

## Projects Information

### ActorDB

ActorDB is a distributed SQL database that follows the actor model. It is designed to work with databases that have the same schema, but serve different customers. Common data can exist in the form of a key/value table.

A schema is an Actor Type. An Actor is a relational database of a certain Actor Type. So, for example, you might have a `blog` Actor Type, and an Actor called `example_company_blog` of type `blog`. Each actor runs in a cluster. A cluster consists of an odd number of nodes that communicate to each other with the Raft protocol. One node is a writer, others are followers. ActorDB also supports Actor KV, a key/value table that is sharded across all clusters. An Actor KV type can have multiple columns and foreign keys to regular tables.

SQLite is used for the storage and SQL layers.

* [Website](https://www.actordb.com/)
* [Documentation](https://www.actordb.com/docs-about.html)
* [GitHub](https://github.com/biokoda/actordb)

## Dolt

The Dolt team define their product as //git for databases//. Dolt allows us to run git operations against a dataset, including clone, pull, push, branch and commit. Databases can be shared via DoltHub in the same way you'd share code via GitHub. Another service, DoltHub, allows you to share data with your team without making them public.

It support SQL in the MySQL dialect, as well as the MySQL protocol. Any MySQL client should be able to connect to Dolt. It can also replicate data from a MySQL server, like a normal MySQL replica.

* [GitHub](https://github.com/dolthub/dolt)
* [Documentation](https://docs.doltlab.com/)
* [DoltHub](https://www.dolthub.com/)
* [DoltLab](https://www.doltlab.com/)

### immudb

immudb is a multi-model database. When a client writes data, an additional cryptographic proof of authenticity is associated to the data. When a client reads data, it can verify the cryptographic proof to be sure that the database was not artificially modified. Or it can skip this step for better performance.

immudb is a relational, key/value and dodument databases. These models use different APIs and cannot interact with each other. A subset of SQL and transactions are supported for relational data.

For relational data, updates only happen at a logical level. It is always possible to query past data. However, deletes are unsupported. It is possible to drop a table, in which case it reimains in the logs but cannot be undropped. Key/value data support expiration.

* [Website](https://immudb.io/)
* [Documentation](https://docs.immudb.io/master/)
* [GitHub](https://github.com/codenotary/immudb)

### NoSQL

NoSQL is a relational database that doesn't implement SQL. Instead, it uses a set of simple and fast UNIX tools. Each tool replaces an SQL operator and its output can be piped to another operator. It makes use of GNU tools, as well as purpose-created tools written in C or Awk. NoSQL follows the //Operator-Stream Paradigm//.

* [Website](http://www.strozzi.it/cgi-bin/CSA/tw7/I/en_US/NoSQL)
* [Wikipedia](https://en.wikipedia.org/wiki/Strozzi_NoSQL)
* [Philosophy of NoSQL](http://www.strozzi.it/cgi-bin/CSA/tw7/I/en_US/NoSQL/Philosophy%20of%20NoSQL)

## TypeDB

TypeDB implements a query language called TypeQL. It allows us to define complex data types with attributes and ontologic relationships. The idea is to provide simple building blocks that allow to build complex schemas and rules. Queries can find data based on their relationships.

TypeDB has replication, with one leader and any number of followers. Encryption is also supported.

* [Website](https://typedb.com/)
* [TypeQL](https://github.com/typedb/typeql)
* [GitHub](https://github.com/typedb/typedb)
* [TypeDB philosophy](https://typedb.com/philosophy)
---

# About This Project

## Contributing

See the [CONTRIBUTING.md](https://github.com/Vettabase/awesome-innovative-databases/blob/main/CONTRIBUTING.md) file.

## How to Thank Us

If you're the maintainer of a resource we linked, we encourage you to show in your resource an
[Awesome mentioned badge](https://github.com/sindresorhus/awesome/blob/main/awesome.md#awesome-mentioned-badge).

Simply paste this code in your `README.md` file:

```
[![Mentioned in Awesome Innovative Databases](https://awesome.re/mentioned-badge.svg)](https://github.com/Vettabase/awesome-innovative-databases)
```

The result will look like the following:

[![Mentioned in Awesome MariaDB](https://awesome.re/mentioned-badge.svg)](https://github.com/Vettabase/awesome-mariadb)

## Copyright and License

Copyright 2024 Vettabase Ltd and contributors.

Awesome MariaDB list is licensed under [CC BY-SA 4.0 license](https://creativecommons.org/licenses/by-sa/4.0/).
