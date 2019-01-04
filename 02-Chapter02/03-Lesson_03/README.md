# ND111 - SQL for Data Analysis `Lesson03`

#### Tags
* Author : AH Uyekita
* Title  :  _SQL Aggregations_
* Date   : 17/12/2018
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** [Derek Steer][derek]

[derek]: https://modeanalytics.com

#### Exercises

All exercises of this chapter I have stored in the Mode Analytics platform.

[Solutions in Mode Analytics - Part 1][sol_ma1]
[Solutions in Mode Analytics - Part 2][sol_ma2]

[sol_ma1]: https://modeanalytics.com/ah_uyekita/reports/9a9bccedfc63
[sol_ma2]: https://modeanalytics.com/ah_uyekita/reports/67d5f05b7443

********************************************************************************

## Aggregations Functions

This is functions return a single row with the aggregated value.

* sum;
* min;
* max;
* mean, etc.

#### NULL

NULL is no a value, it is different from ZERO or a space, for this reason you can not use equal (`=`) to find it, for do so you must use `IS`. The NULL is ignored in all aggregatins functions, and it is defined as a property of the data.

For the _Parch and Posey_ dataset, NULL is equal to zero.

```sql
WHERE something IS NULL
WHERE something IS NOT NULL
```

##### NULLs - Expert Tip

There are two common ways in which you are likely to encounter NULLs:

* NULLs frequently occur when performing a LEFT or RIGHT JOIN. You saw in the last lesson - when some rows in the left table of a left join are not matched with rows in the right table, those rows will contain some NULL values in the result set.
* NULLs can also occur from simply missing data in our database.

## Functions

#### COUNT()

Count the number of rows. If the entire line has only NULLs, this line will be noted counted.

Simple Example:
```sql
SELECT COUNT(*)
FROM accounts;
```

Example with filter
```sql
SELECT COUNT(*) AS order_count
FROM some_table
WHERE any_column > 100 AND any_column < 200;
```

Example with column selection
```sql
SELECT COUNT(account.id)
FROM accounts;
```
#### SUM()

Perform the summation among rows. You must define which columns will be applied the sum function.

```sql
SELECT SUM(poster_qty)
FROM demo.orders;
```

#### MAX() and MIN()

Return a rows with the minimun or maximum of a given column.

```sql
SELECT MAX(poster_qty) AS max_poster_qty,
       MIN(standard_qty) AS min_standard_qty
FROM demo.orders;
```

#### GROUP BY

Divide the non-grouped column into groups, which means the aggregated function will be calculated by group.

* The GROUP BY always goes between WHERE and ORDER BY.

Example 1:
```sql
SELECT a.name, o.occurred_at
FROM accounts a
JOIN orders o
ON a.id = o.account_id
ORDER BY o.occurred_at
LIMIT 1;
```
Same example but indexing by number:
```sql
SELECT a.name, o.occurred_at
FROM accounts a
JOIN orders o
ON a.id = o.account_id
ORDER BY 2
LIMIT 1;
```

_OBS.: The index used in ORDER BY clause is to refence o.occurred_at._

#### DISTINCT

DISTINCT is always used in SELECT statements, and it provides the unique rows for all columns written in the SELECT statement. Therefore, you only use DISTINCT once in any particular SELECT statement.

```sql
SELECT DISTINCT column1, column2, column3
FROM table1;
```

#### HAVING

>HAVING is the “clean” way to filter a query that has been aggregated, but this is also commonly done using a subquery. Essentially, any time you want to perform a WHERE on an element of your query that was created by an aggregate, you need to use HAVING instead.

Note extracted from the class notes.

```sql
SELECT s.id, s.name, COUNT(*) num_accounts
FROM accounts a
JOIN sales_reps s
ON s.id = a.sales_rep_id
GROUP BY s.id, s.name
HAVING COUNT(*) > 5
ORDER BY num_accounts;
```

## DATE

To GROUP BY a date is quite complicated because each time is (obviously) different, for this, reason is necessary to "round" the time/date to group them.

#### DATE_TRUNC

Common trunctions are:

* day;
* month, and;
* year.

Sintaxe:

DATE_TRUNC(‘[interval]’, time_column)

Where:

* microsecond
* millisecond
* second
* minute
* hour
* day
* week
* month
* quarter
* year
* century
* decade
* millenium

For further explanaition about [date][link_more]

[link_more]: https://blog.modeanalytics.com/date-trunc-sql-timestamp-function-count-on/

```sql
SELECT demo.accounts.name,
       DATE_TRUNC('month', demo.orders.occurred_at) AS year_month,
       SUM(demo.orders.gloss_amt_usd) AS sum_gloss_usd
FROM demo.orders
JOIN demo.accounts
ON demo.orders.account_id = demo.accounts.id
WHERE demo.accounts.name = 'Walmart'
GROUP BY year_month, demo.accounts.name
ORDER BY sum_gloss_usd DESC
LIMIT 1;
```

#### DATE PART

Extract part of the date

## CASE

Create a new column, derivate column, with a kind classification (assign a value into this new column according to the statment).

```sql
SELECT account_id,
       occurred_at,
       total,
       CASE WHEN total > 500 THEN 'Over 500'
            WHEN total > 300 AND total <= 500 THEN '301 - 500'
            WHEN total > 100 AND total <= 300 THEN '101 - 300'
            ELSE '100 or under' END AS total_group
FROM demo.orders
LIMIT 10;
```
Creates the total_group column.

#### With AGGREGATION

Combining the CASE clause with aggregations function could be a power tool, because the WHERE clause only evaluate one statement, using WHEN CASE it is possible to evaluate several staments.

```sql
SELECT demo.orders.account_id,
       demo.orders.total_amt_usd,
       CASE WHEN demo.orders.total_amt_usd >= 3000 THEN 'Large'
            ELSE 'Small' END AS level
FROM demo.orders
LIMIT 10;
```
