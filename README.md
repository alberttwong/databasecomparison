# database comparison
PR from everyone is welcomed!

## OLAP databases
I use the term loosely.   I consider OLAP databases to range from Trino/Presto/Athena (it's federated query engine but people use it like a database), Dremio, ClickHouse, Apache Druid, Apache Pinot, Snowflake, AWS RedShift, GCP BigQuery and others.

This is a good list to show who is in the OLAP database space.  https://benchmark.clickhouse.com/
![Screenshot 2023-08-17 at 12 40 52 PM](https://github.com/alberttwong/databasecomparison/assets/749093/03cb8fa1-a4fe-4324-b6f0-00654e920f7b)

### List of OLAP databases that utilize SIMD (Single Instruction Mutiple Data)
What is database that uses SIMD  https://atwong.medium.com/the-hottest-area-of-database-design-querying-billions-of-rows-per-second-with-simd-aa705fb5dfb6

Here is a list of databases that are known to utilize SIMD.  As you can see, from the ClickHouse Benchmark, databases with SIMD dominate the leaderboard. 
* ClickHouse: https://clickhouse.com/docs/zh/faq/general/why-clickhouse-is-so-fast
* Apache Druid: (maybe? https://imply.io/blog/announcing-druid-0-16-0/)
* StarRocks: https://docs.starrocks.io/en-us/latest/introduction/StarRocks_intro
* QuestDB: https://questdb.io/blog/2020/04/02/using-simd-to-aggregate-billions-of-rows-per-second/
* Rockset: https://rockset.com/blog/rockset-beats-clickhouse-druid-star-schema-benchmark/
* Apache Doris: https://doris.apache.org/docs/1.2/summary/basic-summary/
* SingleStore: https://www.singlestore.com/blog/memsql-processing-shatters-trillion-rows-per-second-barrier/
* DuckDB: https://duckdb.org/faq.html#does-duckdb-use-simd
* AWS RedShift: https://assets.amazon.science/93/e0/a347021a4c6fbbccd5a056580d00/sigmod22-redshift-reinvented.pdf
* TiDB: https://pingcap.medium.com/why-benchmarking-distributed-databases-is-so-hard-2765a26cc2bf

## List of OLAP databases that support primary key to support batch and streaming upsert
Why is primary key support important to batch and streaming insert, update, delete and upsert scenarios. https://atwong.medium.com/list-of-olap-databases-that-support-primary-key-8e42a65fbee3
* StarRocks: https://docs.starrocks.io/en-us/latest/table_design/table_types/primary_key_table
* ClickHouse: https://clickhouse.com/docs/en/optimize/sparse-primary-indexes#a-table-with-a-primary-key
* SingleStore: https://docs.singlestore.com/cloud/create-a-database/understanding-keys-and-indexes-in-singlestore/

### List of OLAP databases that support the MySQL protocol
* Dolt database (OLTP): Dolt is a SQL database you can fork, clone, branch, merge, push and pull just like a Git repository. Connect to Dolt just like any MySQL database to run SQL queries. Use the command line interface to import CSV files, commit your changes, push them to a remote, or merge your teammate’s changes. https://www.dolthub.com/
* StarRocks (OLAP): StarRocks is a next-gen sub-second MPP database for full analytics scenarios, including multi-dimensional analytics, real-time analytics and ad-hoc query. https://www.starrocks.io/
* TiDB (OLTP+OLAP): TiDB is an open-source distributed SQL database that supports Hybrid Transactional and Analytical Processing (HTAP) workloads. It is MySQL compatible and features horizontal scalability, strong consistency, and high availability. https://www.pingcap.com/
* Sphinx Search (Search): Sphinx is a fulltext search engine that provides text search functionality to client applications. https://sphinxsearch.com/
* SingleStore: SingleStore is a proprietary, cloud-native database designed for data-intensive applications. A distributed, relational, SQL database management system that features ANSI SQL support, it is known for speed in data ingest, transaction processing, and query processing. https://docs.singlestore.com/cloud/connect-to-your-workspace/connect-with-mysql/connect-with-mysql-client/

### List of OLAP databases that uses a cost based optimizer (CBO) or rule based optimizer for query execution
* StarRocks: (cbo) https://docs.starrocks.io/en-us/latest/introduction/StarRocks_intro
* ClickHouse: (rbo) https://www.alibabacloud.com/blog/clickhouse-source-code-introduction-the-story-of-sql-queries_597893#:~:text=ClickHouse%20uses%20a%20syntax%20analyzer%20featuring%20recursive%20descent%20analysis.&text=This%20is%20usually%20referred%20to,without%20changing%20the%20query%20semantics.
* Apache Druid: (cbo?) https://www.deep.bi/blog/druid-sql-queries-on-apache-druid
* SingleStore: (cbo) https://docs.singlestore.com/cloud/reference/sql-reference/data-manipulation-language-dml/explain/
* Trino: (cbo) https://trino.io/blog/2019/07/04/cbo-introduction.html
* TiDB: (cbo) https://docs.pingcap.com/tidb/stable/dev-guide-hybrid-oltp-and-olap-queries/

### Data Processing Models of different OLAP databases
* StarRocks: MPP
* Apache Druid: Scatter-Gather
* ClickHouse: MPP
* SingleStore: Scatter-Gather
* Apache Spark: Map-Reduce

### OLAP databases that can run TPC-H benchmarks
What is the difference between TPC-H and TPC-DS? TL-DR; TPC-DS has more difficult SQL-like SQL queries with different types of JOINS compared to TPC-H. Many OLAP systems can't even complete the TPC-H benchmark or the more difficult TPC-DS benchmark.  https://atwong.medium.com/what-is-the-difference-between-tpc-h-and-tpc-ds-benchmarks-cb92fc104c32
* StarRocks: Successful.  See https://www.starrocks.io/blog/benchmark-test
* ClickHouse: Failed. They do not strictly follow the standard SQL syntax. They say to use their modified version of Star Schema Benchmark (SSB) which isn't apples to apples comparison.
* Apache Druid: Failed.  They said: Since Druid was built to solve a specific type of problem, we chose a set of benchmarks typical of Druid's workload that covers the majority of queries we observe in production. Why not use the TPC-H benchmark queries, you may ask? Most of those queries do not directly apply to Druid, and we would have to largely modify the queries or the data to fit the Druid model. See https://druid.apache.org/blog/2014/03/17/benchmarking-druid.html.
* SingleStore: Successful. https://www.singlestore.com/blog/memsql-tpc-benchmarks/

### OLAP databases that can run TPC-DS benchmarks
What is the difference between TPC-H and TPC-DS? TL-DR; TPC-DS has more difficult SQL-like SQL queries with different types of JOINS compared to TPC-H. Many OLAP systems can't even complete the TPC-H benchmark or the more difficult TPC-DS benchmark.  https://atwong.medium.com/what-is-the-difference-between-tpc-h-and-tpc-ds-benchmarks-cb92fc104c32
* StarRocks: Successful.  See https://www.starrocks.io/blog/benchmark-test
* ClickHouse: Failed. They do not strictly follow the standard SQL syntax. They say to use their modified version of Star Schema Benchmark (SSB) which isn't apples to apples comparison.
* Apache Druid: Failed.  They said: Since Druid was built to solve a specific type of problem, we chose a set of benchmarks typical of Druid's workload that covers the majority of queries we observe in production. Why not use the TPC-H benchmark queries, you may ask? Most of those queries do not directly apply to Druid, and we would have to largely modify the queries or the data to fit the Druid model. See https://druid.apache.org/blog/2014/03/17/benchmarking-druid.html.
* SingleStore: Successful. https://www.singlestore.com/blog/memsql-tpc-benchmarks/
