# Performance Optimization

## Postgresql

### EXPLAIN ANALYZE

The structure of a query plan is a tree of plan nodes. Nodes at
the bottom level of the tree are scan nodes: They return raw nodes
from a table.

The different types of scan nodes are:
 * sequential scans
 * index scans
 * bitmap indec scans

If the query requires other operations such as joining, aggregration,
sorting etc. There will be other nodes used for those operations.
Explain has one output of node per the query tree.

There are two costs shown per node, the first cost is the est.
startup cost. The second costr is the est. total cost to execute
the query. The row count is obvious and it is just an estimation of
the total amount of rows output by the node. The width, is the est.
amount of bytes each row is going to take up.

It's important that the cost of an upper level node includes the
cost of all of it's lower level child nodes.

Note that when using the **ANALYZE** option with **EXPLAIN** you
will get the true row count return and the true timings because
**ANALYZE** actually executes the query.

#### Index Scan vs Bitmap Index Scan
**Index** scan reads the index in alternation between table
and index, row at a time while a **Bitmap Index Scan** scans
all index rows before examining the base table.

#### Bitmap Heap Scan
A **Bitmap Heap Scan** is similar to a sequential scan, with
the difference thatn visiting every diskapge, it only visits
the disk pages that is needed. This differs from an **index scan**
because the index is visited row by row in order -- this means
that a disk page may get visited multiple times.

An **index scan** will go through rows one by one reopening disk
pages while a **bitmap index scan** will open up all the necessary
disk pages and grap each row needed from each disk page.

#### Batches
When seeing **Batches** in a query plan. If it exceeds greater
than 1 that means that disk space is going to be used during
the query.


#### Materialize
**Materialize** is a good thing that appears. It means that
it's saving data in memory when needed to be executed multiple
times by a loop. This means that it would only make a call once
in a nested loop even though it may require a model in nine times.


