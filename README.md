# What is potatopage?

Potatopage contains a paginator class called UnifiedPaginator. This is an attempt
to unify various systems of using cursors to provide pagination on AppEngine.

The idea is that the paginator takes a batch_size argument. This controls the pages
for which a cursor will be stored. For example, a batch_size of 2 would mean that
a cursor would be cached on page 0, page 2, page 4 etc. Accessing page 3 would use
the cursor from page 2, read the entire batch between page 2 and 4, and then offset
into the results.