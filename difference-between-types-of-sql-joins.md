<!-- TITLE: Difference Between Types of SQL Joins -->
<!-- SUBTITLE: Inner join, Outer Join, Left Join and more... -->

An SQL JOIN clause is used to combine rows from two or more tables, based on a common field between them. There are different types of joins available in SQL:
# Inner Join
This is the default join operation used when no other keyword (such as left, right or inner) is specified. This type of join returns rows when there is a match in both tables.

# Outer Join
Outer joins can be a Left, a Right, or Full Outer Join. Outer joins are specified with one of the following sets of keywords:

## Left Join or Left Outer Join
The result set of a Left Outer Join includes all rows from the left table specified in the LEFT OUTER clause, not just the ones in which the joined columns match. When a row in the left table has no matching rows in the right table, the associated result set row contains null values for all select list columns coming from the right table.

## Right Join or Right Outer Join
A Right Outer Join is the reverse of a Left Outer Join. All rows from the right table are returned. Null values are returned for the left table any time a right table row has no matching row in the left table.

## Full Join or Full Outer Join
A Full Outer Join returns all rows in both the Left and Right tables. Any time a row has no match in the other table, the select list columns from the other table contain null values. When there is a match between the tables, the entire result set row contains data values from the base tables.

The following diagram shows a visual representation of these types of SQL joins, taken from the article [Visual Representation of SQL Joins](https://www.codeproject.com/Articles/33052/Visual-Representation-of-SQL-Joins "read article").

![Visual Sql Joins V 2](/uploads/sql/visual-sql-joins-v-2.png "Visual Sql Joins V 2"){.align-center}