# awesome-innovative-databases
A curated list of potentially game-changing database systems.

This list is a result of the constant research activities we do at [Vettabase](https://vettabase.com).

We also have a [LinkedIn page](https://www.linkedin.com/showcase/awesome-innovative-db).

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) Inspired by the `awesome-*` trend on GitHub.

**Table of Contents**

* [Active Projects](#active-projects)
* [Cemetery of Great Ideas](#cemetery-of-great-ideas)
* [Projects Information](#projects-information)
* [About](#about-this-project)

## Active Projects

* [Dolt](#dolt) - Git for relational data, compatible with MySQL.
* [immudb](#immudb) - Immutable, cryptographically verified, multi-model database.
* [MobilityDB](#MobilityDB) - A geospatial trajectory data management and analysis database.
* [RisingWave](#risingwave) - An SQL streaming database.
* [Tarantool](#tarantool) - A framework for data storage an processing.
* [TypeDB](#typedb) - Allows to define complex types and ontologies.
* [Seafowl](#seafowl) - For analytics, built with web applications in mind.
* [XTDB](#xtdb) - A transactional, bitemporal database based on the JVM.

## Cemetery of Great Ideas

This is a very sad place. But some necromancer might decide to bring one of these projects back, as long as they are [Open Source](https://opensource.org/osd) / [Free Software](https://www.gnu.org/philosophy/free-sw.en.html).

We bury a project in this cemetery if the most recent commit or public release is at least 2 years old, or if the project was officially discontinued.

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

### Dolt

The Dolt team define their product as _git for databases_. Dolt allows us to run git operations against a dataset, including clone, pull, push, branch and commit. Databases can be shared via DoltHub in the same way you'd share code via GitHub. Another service, DoltHub, allows you to share data with your team without making them public.

It support SQL in the MySQL dialect, as well as the MySQL protocol. Any MySQL client should be able to connect to Dolt. It can also replicate data from a MySQL server, like a normal MySQL replica.

* [GitHub](https://github.com/dolthub/dolt)
* [Documentation](https://docs.doltlab.com/)
* [DoltHub](https://www.dolthub.com/)
* [DoltLab](https://www.doltlab.com/)
* [Dolt database: first impressions](https://vettabase.com/dolt-database-first-impressions/)

### immudb

immudb is a multi-model database. When a client writes data, an additional cryptographic proof of authenticity is associated to the data. When a client reads data, it can verify the cryptographic proof to be sure that the database was not artificially modified. Or it can skip this step for better performance.

immudb is a relational, key/value and document database. These models use different APIs and cannot interact with each other. A subset of SQL and transactions are supported for relational data.

For relational data, updates only happen at a logical level. It is always possible to query past data. However, deletes are unsupported. It is possible to drop a table, in which case it remains in the logs but cannot be undropped. Key/value data support expiration.

* [Website](https://immudb.io/)
* [Documentation](https://docs.immudb.io/master/)
* [GitHub](https://github.com/codenotary/immudb)

### MobilityDB

MobilityDB is a PostgreSQL extension. It is a database for geospatial data management and analysis of moving objects.

When an object is moving, we have its position at several points in time. The position of an object in the interval between two observations is unknown by definition. However, MobilityDB tries to calculate the position at any point in time based on the previous and next position information, and the object's speed and direction. To do so, MobilityDB implements its own type system: it has types that represent the position, direction and speed of an object, as well as temporal versions of the most common type, to represent an information as a point in time.

While calculating the trajectories, MobilityDB eliminates the point that are not useful for this purpose, for example because an object remained still for some time.

* [Website](https://www.osgeo.org/projects/mobilitydb/)
* [GitHub](https://github.com/MobilityDB/MobilityDB)

### RisingWave

RisingWave is an SQL streaming database. In RisingWave, several integrations to external data sources are available. This includes Kafka, that can be used to capture data changes (CDC) from most databases. Integrations allow you to import data by creating a Source, or export data by creating a Sink. These objects can be created with SQL commands.

Imported data can optionally be persisted into local tables. You can also create materialized views, that read data from local tables or directly from the data source. Data can also be inserted directly via the SQL INSERT statement. A table can also contain additional columns, for data that are not imported from the source.

It is possible to query data via SQL, using PostgreSQL dialect and protocol. RisingWave also allows to run JOINs that involve multiple data sources.

* [RisingWave](https://risingwave.com/)
* [Documentation](https://docs.risingwave.com/docs/)
* [GitHub](https://github.com/risingwavelabs/risingwave)
* [Playground](https://cloud.risingwave.com/auth/signin/)

### NoSQL

NoSQL is a relational database that doesn't implement SQL. Instead, it uses a set of simple and fast UNIX tools. Each tool replaces an SQL operator and its output can be piped to another operator. It makes use of GNU tools, as well as purpose-created tools written in C or Awk. NoSQL follows the _Operator-Stream Paradigm_.

* [Website](http://www.strozzi.it/cgi-bin/CSA/tw7/I/en_US/NoSQL)
* [Wikipedia](https://en.wikipedia.org/wiki/Strozzi_NoSQL)
* [Philosophy of NoSQL](http://www.strozzi.it/cgi-bin/CSA/tw7/I/en_US/NoSQL/Philosophy%20of%20NoSQL)

### Tarantool

Tarantool is a NoSQL database for data storage and processing. Tarantool has two storage engines: memtx to store data in-memory, and vynil to store data on-disk. It is also a Lua application server, which allows to store data logic in the database itself. It can interact with several types of data sources, making it a powerful tool for data integration.

Tarantool uses spaces instead of tables. A space can be schemaless, but a schema can also be specified on creation or even later. Schemas can be defined in YAML, or in Lua files that are executed when Tarantool starts.

Tarantool supports replication. Master-masrer replication is not recommended, but supported. Replication is asynchronous by default, but it's possible to use synchronous transactions, to make changes that will be immediately replicated. Sharding is also supported. Each shard can be a replica set.

* [Website](https://www.tarantool.io/)
* [Documentation](https://www.tarantool.io/en/doc/latest/)
* [GitHub](https://github.com/tarantool/tarantool)

### TypeDB

TypeDB implements a query language called TypeQL. It allows us to define complex data types with attributes and ontologic relationships. The idea is to provide simple building blocks that allow to build complex schemas and rules. Queries can find data based on their relationships.

TypeDB has replication, with one leader and any number of followers. Encryption is also supported.

* [Website](https://typedb.com/)
* [TypeQL](https://github.com/typedb/typeql)
* [GitHub](https://github.com/typedb/typedb)
* [TypeDB philosophy](https://typedb.com/philosophy)

### Seafowl

Seafowl is an SQL database, exclusively for analytics.

Seafowl was designed for modern web applications. It can be queried via HTTP and it will return JSON results. By design, it is possible to run it in a CDN, cache some queries via [Varnish HTTP Cache](https://varnish-cache.org/), or leverage a web browser cache via `fetch()`. It also supports cache validity checks using HTTP ETags.

Data files are stored in the [Apache Parquet](https://parquet.apache.org/) format. Data can be loaded as Apache Parquet or CSV.

High availability is supported using an external PostgreSQL database as a catalog. In a single-node deployment, a local SQLite database is used as a catalog.

* [Website](https://seafowl.io/)
* [Documentation](https://seafowl.io/docs/getting-started/introduction)
* [GitHub](https://github.com/splitgraph/seafowl)

### XTDB

XTDB is a transactional, immutable and bitemporal database. Users don't have to do anything to version data, or to specify that by default they want to only see current data. But they can use some special syntax to query the past. XTDB is schemaless, which solves the complex problem of versioning data with a schema that can change over time.

XTDB runs on the JVM. It includes an HTTP server that can be used to send SQL queries and receive the results as JSON. However, it also implements a Datalog API, implemented in Java, Clojure and Koitlin (all of them are JVM-based languages). It's also possible to extend a transaction logic with a Clojure function, for example to validate data.

In XTDB, updates and deletes are logical, and an old version of the rows remains virtually forever. However, the Datalog `evict` command can be used to physically delete data that are not needed anymore, so that a database won't grow forever.

* [Website](https://xtdb.com/)
* [Documentation](https://docs.xtdb.com/)
* [GitHub](https://github.com/xtdb/xtdb)

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

[![Mentioned in Awesome Innovative Databases](https://awesome.re/mentioned-badge.svg)](https://github.com/Vettabase/awesome-innovative-databases)

## Copyright and License

Copyright 2024 Vettabase Ltd and contributors.

The Awesome Innovsative Databases list is licensed under [CC BY-SA 4.0 license](https://creativecommons.org/licenses/by-sa/4.0/).
