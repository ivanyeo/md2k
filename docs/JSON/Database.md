#Database table formats

## Proposed Cassandra table layout:

```SQL
CREATE TABLE table_name (

tsuuid uuid,

date text,
timestamp timeuuid,

delta decimal,
values list<string>,
blob_value blob,

PRIMARY KEY (tsuuid, date), timestamp)

);
```
