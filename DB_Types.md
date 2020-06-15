# Time series databases

Time series databases are designed based on the idea that data changes through time. Some visualize this type of data bases as sequence of data points over time, stored in time order. Time is the central piece of times-series databases. For each "timestamp" we have records for the metrics. (Table example)

There are two ways of managing the data, each table for each metric where the metric is the ID of the table or collection of different metrics per time.

An example of the format here:

![](TS-DB.png)

You may wonder, if there are a lot of databases that manage timestamps, for example SQL. Why use them? Time series databases are highly optimized for managing data using time as an identifier. The idea of the optimizations comes from this assumptions of the use of time series data base:

- The data that arrives is almost always recorded as a new entry.
- The data typically arrives in time order.
- Time is a primary axis.

## Examples 

- InfluxDB
- Prometheus
- Timescale


# In-memory databases

Usually classic database as SQL, store all the information in a hard drive or in solid state drives. As you may know the this type of memory is much slower to access compared to the Random Access Memory (RAM). Therefore in tasks where the database response time is critical, In-Memory databases comes handy. Given that the main characteristic of this kind of database are that they operates on RAM memory; this allows really fast response times. 

Application of this databases can be gaming headboards, where new scores are created in seconds. Then, in order to have the database updated in real time, a databases with fast memory reading comes handy.


## What happens if the machine shuts down?

For know there are some solutions for this problem:

- Snapshots: Each amount of time the database creates a backup of the data in a non volatile memory, this allow to restore the data if something goes wrong with the energy supply:

- NVRAM technology: NVRAM stands for Non-Volatile Random Access Memory. This means that the database is saved on a RAM that does not wipe-out the data if the energy stream cuts.



# Search Engine databases
Search-engine databases are characterized for being optimizad for searching data content. Indexes are used to categorize similar characteristics among the data. This types of databases are made for working with data that is not structured, long registers and normal registers. Really useful for task where specific data retrival of not structured data is constantly done. 


# References

- https://aws.amazon.com/es/nosql/
- https://severalnines.com/database-blog/introduction-time-series-databases
- https://www.timescale.com
- https://www.profesionalreview.com/2018/12/08/nvram/






# **Time series**

|
 | InfluxDB | TimescaleDB | OpenTSDB | Graphite |
| --- | --- | --- | --- | --- |
| Developer | Paul Dix | Timescale Inc. | Benoit Sigoure | Orbitz Worldwide, Inc |
| Language supported | SQL, Go, Java, PHP, Python, lisp, Clojure and more | .Net, C, C++, Delphi, Java JavaScript Perl PHP Python R Ruby Scheme Tcl | Erlang, Go, Java, Python, R, Ruby | JavaScript (Node.js), Python |
| Operating system | Work on all current operating systems | Timescale cloud, Docker, MacOS, Windows, Ubuntu, Debian, Red hat, Azure | Windows, Linux | Linux, Unix |
| Focus on | &quot;It is designed to handle high write and query loads and provides a SQL-like query language called InfluxQL for interacting with data&quot; -Influxdb.com | Is optimized for fast ingest and complex queries. It speaks &quot;full SQL&quot; and is correspondingly easy to use like a traditional relational database, yet scales in ways previously reserved for NoSQL databases. | Collect, store and display metrics of various computer systems (network gears, operating systems, applications), and generate readable data graphs easily. | Monitors and graphs numeric time-series data such as the performance of computer systems. |
| Advantages | Efficiency, resistance, good documentation, easy to install | TimescaleDB is automatically sharded and has no influence from the users&#39; perspective. | The advantage of OpenTSDB lies in the ability to write and store data, owed largely to the bottom layer&#39;s dependency on HBase. | Render any graph, Great functions to apply on timeseries, Well supported integrations |
| Disadvantages | if misconfigured, performance begins to suffer, does not come with support for distributed deployments | Distributed hypertables have certain limitations | The disadvantage lies in the lack of ability to query and analyze data. Although many optimizations have been made in queries, these optimizations are not applicable to all query scenarios. | Graphite requires additional tools and effort to support alarm generation. |

# **In-memory**

|
 | MemSQL | Redis | VoltDB | Tarantool |
| --- | --- | --- | --- | --- |
| Developer | MemSQL Inc. | Salvatore Sanfilippo | Michael Stonebraker | Mail.Ru Group |
| Language supported | Bash, C, C#, Java, JavaScript (Node.js), Python | C, C#, C++, Clojure, Crystal, D, Dart, Elixir, Erlang, Fancy, Go, Haskell, Haxe, Java, JavaScript (Node.js), Lisp, Lua, MatLab, Objective-C, OCaml, Pascal, Perl, PHP, Prolog, Pure Data, Python, R, Rebol. Ruby, Rust, Scala, Scheme, Smalltalk, Swift, Tcl, Visual Basic | C#, C++, Erlang, Go, Java, JavaScript, PHP, Python | C, C#, C++, Erlang, Go, Java, JavaScript, Lua, Perl, PHP, Python, Rust |
| Operating system | Linux | BSD, Linux, OS X, Windows | Linux, OS X | BSD, Linux, macOS |
| Focus on | Deliver maximum performance for transactional and analytical workloads with familiar relational models | Is focused on streaming, with support for a print-like API, pipelining, Pub/Sub, and connection pooling. stephensearles. | VoltDB focuses specifically on fast data. That is, applications that must process large streams of data quickly | focus on a task queue application using Tarantool as an application server and a database. |
| Advantages | Distributed, Realtime | Allows storing key and value pairs as large as 512 MB, uses its own hashing mechanism called Redis Hashing | offers fast ingestion and real-time analytics on the inbound stream, enables applications to act on events in real time | Quick and ease of use, Tarantool can serve an order of magnitude more requests per second |
| Disadvantages | supports fewer programming languages than other options | The whole dataset always resides in RAM, | it is not good at problems requiring lots of column scanning | Unpredictable write speed, Unpredictable read speed |

# **Search**

|
 | Elasticsearch | Splunk | Solr | ArangoDB |
| --- | --- | --- | --- | --- |
| Developer | Shay Banon | Michael Baum, Erik Swan and Rob Das | Yonik Seeley | ArangoDB GmbH |
| Language supported | .Net, Groovy, Community, Contributed Clients, Java, JavaScript, Perl, PHP, Python, Ruby | C#, Java, JavaScript, PHP, Python, Ruby | .Net, Erlang, Java, JavaScript, any language that supports sockets and either XML or JSON, Perl, PHP, Python, Ruby, Scala | C#, C++, Clojure, Elixir, Go, Java, JavaScript (Node.js)PHP, Python, R, Rust |
| Operating system | All OS with a Java VM | Linux, OS X, Solaris, Windows | All OS with a Java VM | Linux, OS X, Windows |
| Focus on | It allows you to store, search, and analyze big volumes of data quickly and in near real time | used for searching, monitoring, and examining machine-generated Big Data through a web-style interface | Scalability and fault tolerance. Solr is widely used for enterprise search and analytics use cases and has an active development community and regular releases | Attach metadata to mounted routes, middleware and child routers that affects how requests and responses are processed or provides API documentation |
| Advantages | Lots of search options, Document-oriented, speed, scalability | Analyzes the aggregate of logs from a big service cluster, Finds real-time logs and with faster speed | Splits read and write load and operations, Load distribution for search queries | Graphs and documents in one DB, Intuitive and rich query language |
| Disadvantages | Elasticsearch is not ACID-compliant out of the box, should not be used as a primary persistence store | Splunk can prove expensive for large data volumes, Dashboards are functional but not as effective as some other monitoring tools | Increased latency (sum of tracking and Solr replication latency), Occasional large IO load to replicate large merges | The implementation is not optimized for very long-running or very voluminous operations, and may not be usable for these cases. |
