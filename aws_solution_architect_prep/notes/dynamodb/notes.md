* An item is a collection of attributes inside a table. It can not be
bigger than 400KB

* Dynamodb is a global service and partitioned regionally.
* Dynamodb stored data into three replicas in independent AZ
* can survive failure of a AZ

Dynamodb has two capacity modes:
--- Provisioned throughput
--- on-demand(automatically scales and bills per request)
Introduction
In this guide, we are going to learn how to provision capacity for DynamoDB.

By setting read and write capacity, we can tell Amazon Web Services how much hardware capacity to provision to meet our performance capacity.

Provisioned throughput gives us the ability to change read and write performance capacity during table creation or even as an update any time after.


SETUP
We need to understand the difference between eventually consistent and strongly consistent data:

•Eventually consistent: A read request immediately after a write operation might not show the latest change but costs less in terms of capacity.

•Strongly consistent: The most up-to-date data.

Most operations are eventually consistent by default but can usually be changed in your calls.

We also need to understand what is meant by units of read/write capacity:

•A unit of read capacity: 1 strongly consistent read per second or two eventually consistent reads per second for items as large as 4 KB

•A unit of write capacity: 1 write per second for items up to 1KB







fORMULA
Read Capacity



(ITEM SIZE (rounded up to the next 4KB multiplier) / 4KB) * # of items
(Round up to the nearest 4 KB multiplier)


Write Capacity



(ITEM SIZE (rounded up to the next 1KB multiplier) / 1KB) * # of items
(Round up to the nearest 1 KB multiplier)




EXAMPLE #1 READ CAPACITY



We have an item size of 3 KB and we want to read 80 (strongly consistent read) items per second per table. What is the read capacity required?

The formula to determine the total number of read operations is the ITEM SIZE (rounded up to the next multiple of 4 KB, since, again, we can’t group multiple items together) / 4 KB. In this example, we take 3, round it up to 4, and divide it by 4, which gives us 1 read capacity. However, we want to read 80 of these 3 KB items at the same time, so we need to multiply our result by 80, and we end up with 80 for our read throughput capacity.



80 * (3KB (round up to 4) / 4KB)
80 * 1 = 80 required provisioned read throughput


If you use eventually consistent reads then you can cut that number in half because you get twice as many reads per second. We end up with 40 for our read capacity.

♣Eventually consistent reads would cut that in half:



(80 * 1) / 2 = 40 required read capacity


EXAMPLE #2 WRITE CAPACITY



We need 10 writes per second, and we have an item of size 1.5KB, how much throughput is required?

Let’s take our item size of 1.5 KB, and round it up to 2KB, then divide that by 1KB. We take that result, which is 2, and we multiply it by the number of items of that size we want to write per second. In this case, that’s 2 times 10, which gives us 20 write capacity units.



•(ITEM SIZE (1.5KB) / 1 KB) x 10 = 20 capacity units
This is even simpler than reads, because we don’t have to worry about eventually consistent or strongly consistent.



SECONDARY INDEXES



READ

Read capacity uses the same read/write capacity from parent table.

♣If you read only index keys and projected attributes, the calculations are the same.

♣You calculate using the size of the index entry, not the table item size

♣Rounded up to the nearest 4 KB.

♣If queried attributes aren’t projected attributes or keys, we get extra latency and read capacity cost.

♣You use read capacity from the index AND for every item from the table, not just the attribute needed.



WRITE

When you add, update, or delete an item in a table, the local secondary index also consumes write capacity units. You’re not only using write capacity for the table update but also for the local secondary index. The cost of writing an item to a local secondary index depends on a few things:

•If you write a new item to the table and that item defines an indexed attribute, or if you update an existing item and write an indexed attribute that was previously undefined, that will cost you one write operation to put the item in the index.

•If you change the value of an indexed key attribute, two writes are required: one to delete the previous item from the index and another to put the new item into the index.

•If an update deletes an item that was in the index, one write is required to delete the item from the index.

NOTE: This assumes that each item in the index is less than or equal to 1 KB.



GLOBAL SECONDAY INDEXES



READS

The biggest difference between global and local secondary indexes is that global indexes have their own throughput capacity, separate from that of the table’s capacity. If you query data from the global index and all that data is projected into the index, then the table will not consume any of its read capacity.

When you Put, Update, or Delete items in a table, the global indexes on that table are also updated, and the index updates consume index write capacity units, not the table’s write capacity units.



WRITES

♣Putting, Updating, or Deleting items in a table consumes the index write capacity units.

♣The cost of writing an item to a global index depends on a few things, and those are identical to the local secondary index rules.



* Read Capacity Units. A read capacity unit represents one strongly consistent read per second, or two eventually consistent reads per second, for an item up to 4 KB in size.
