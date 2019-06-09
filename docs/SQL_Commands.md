
## 1. Common Table Expressions CTE

Common Table Expressions or CTE’s  were introduced in SQL Server version 2005. 
A CTE is a temporary result set that you can use inside in a following CTE and you can reference within another 
Select, Insert, Update, or Delete statement. 

There are two types recursive and non-recursive.

Non recursive CTE

Some advantages of using Common Table Expressions:

- recursive queries, like walking up a hierarchy tree - that is extremely tricky and cumbersome without a CTE
- When you want to use one of the ranking functions like `ROW_NUMBER()`, `RANK()`, `NTILE()`
- Essentially in any case where you need to select a few rows/columns first, based on some criteria, and then do something with these like
  a final select, delete, update or insert.
- Very useful to remove duplicates rows.



## 2. ROW_NUMBER() Function

It is a ranking function that assigns a sequential number to each row to which it applied beginning with one.

* Sintaxe


ROW_NUMBER() OVER (PARTITION BY expression ORDER BY expression) 

<pre><code>SELECT 
  ROW_NUMBER() OVER ( ORDER BY type) as RowIncrement, 
  ROW_NUMBER() OVER ( PARTITION BY type ORDER BY type) as RowIncrementbyPartition, name , type,  create_date
FROM sys.objects  
ORDER BY type ASC;
</code></pre>
