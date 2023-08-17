# database comparison

## OLAP databases

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
