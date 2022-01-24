## Numbering Functions
Numbering functions are simply a subgroup of analytic functions. Numbering functions simply assign integer values to each row, depending on their position in the specified window.

## Row Numbering in BigQuery
- ROW_NUMBER is an analytic function.
- ROW_NUMBER generates a series of temporary values that are assigned to figures, and is calculated dynamically based on when the query is executed.

### Example
|x|rank|dense_rank|row_num|
|:-:|:-:|:-:|:-:|
|1|1|1|1|
|2|2|2|2|
|2|2|2|3|
|6|3|4|4|
**Row number for x=6 is 4**

### ROW_NUMBERING with Partitioning
The ROW_NUMBER can also be paired with the PARTITION BY clause. So, when the partition limit is crossed, the counter is reset, and begins from 1 again. Partitions can have several values, such as 1,2, 3, and so on, and when it’s reset, the counter starts from 1, 2, and 3 again.
