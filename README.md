# database comparison
PR from everyone is welcomed!

## OLAP databases
I use the term loosely.   I consider OLAP databases to range from Trino/Presto/Athena, Dremio, ClickHouse, Apache Druid, Apache Pinot, Snowflake, AWS RedShift, GCP BigQuery and others.

This is a good list to show who is in the OLAP database space.  https://benchmark.clickhouse.com/


### Built with SIMD (Single Instruction Mutiple Data)
What is database that uses SIMD  https://atwong.medium.com/the-hottest-area-of-database-design-querying-billions-of-rows-per-second-with-simd-aa705fb5dfb6
Here is a list of databases that are known to built with SIMD

* ClickHouse https://clickhouse.com/docs/zh/faq/general/why-clickhouse-is-so-fast
* Apache Druid (maybe? https://imply.io/blog/announcing-druid-0-16-0/)
* StarRocks https://www.starrocks.io/feature
* QuestDB https://questdb.io/blog/2020/04/02/using-simd-to-aggregate-billions-of-rows-per-second/
* Rockset https://rockset.com/blog/rockset-beats-clickhouse-druid-star-schema-benchmark/
* Apache Doris https://doris.apache.org/docs/1.2/summary/basic-summary/

## List of OLAP databases that support primary key to support batch and streaming upsert
Why is primary key support important to batch and streaming insert, update, delete and upsert scenarios. https://atwong.medium.com/list-of-olap-databases-that-support-primary-key-8e42a65fbee3
* StarRocks: https://docs.starrocks.io/en-us/latest/table_design/table_types/primary_key_table
* ClickHouse: https://clickhouse.com/docs/en/optimize/sparse-primary-indexes#a-table-with-a-primary-key

### List of databases that support the MySQL protocol
* Dolt database (OLTP): Dolt is a SQL database you can fork, clone, branch, merge, push and pull just like a Git repository. Connect to Dolt just like any MySQL database to run SQL queries. Use the command line interface to import CSV files, commit your changes, push them to a remote, or merge your teammate’s changes. https://www.dolthub.com/
* StarRocks (OLAP): StarRocks is a next-gen sub-second MPP database for full analytics scenarios, including multi-dimensional analytics, real-time analytics and ad-hoc query. https://www.starrocks.io/
* TiDB (OLTP+OLAP): TiDB is an open-source distributed SQL database that supports Hybrid Transactional and Analytical Processing (HTAP) workloads. It is MySQL compatible and features horizontal scalability, strong consistency, and high availability. https://www.pingcap.com/
* Sphinx Search (Search): Sphinx is a fulltext search engine that provides text search functionality to client applications. https://sphinxsearch.com/
