In mysql we many times need to know the first id of current or last partition to feed it in select queries. For instance, if you want to scan last 2-3 partitions for given conditions. This is what my requirement was when I wrote this query to fetch the starting (first) id of the given partition.

`SELECT floor(max(col_name) / 10000000) * 10000000 - 10000000 * n from table_name;`

Where

    col_name is the name of the column on which our table is partitioned.

    n is the partition number

	0 → current partition 
	1 → last partition 
	2 → second last partition and so on

    table_name: is the partitioned table

    10000000 is the size of every partition (This query works when size of every partition is equal)


For instance
I want to fetch the rows having status = 2 from last week's entries.

query→ 
`select * from table_name where status = 2 and created_at > '04-01-2016'`

This query is not using any partition hence will be taking huge time, even when created_at is indexed.

**Optimizing:**

    (Scanning 3 partitions as I know 3 partitions are used in a week)

`select * from table_name where status = 2 and column_name > (SELECT floor(max(col_name) / 10000000) * 10000000 - 10000000 * 3 from table_name;);`

Using partitions instead of index will make your query a lot faster.

**Creating stored function**

`CREATE FUNCTION partitionFirstId (partitionId INT(12) UNSIGNED) RETURNS INT(12) DETERMINISTIC
RETURN (SELECT floor(max(order_id) / 10000000) * 10000000 - 10000000 * partitionId from fulfillment_recharge)`

So that you don't have to write the whole sub query every time but just a function call-

`select * from table_name where status = 2 and column_name > (select partitionFirstId(?))`

And to view list of stored functions/procedure created in your mysql, you can refer: **information_schema.routines**

`Select * from INFORMATION_SCHEMA.ROUTINES;`

Stayed tuned for more mysql **hacks**.
