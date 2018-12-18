# ND111 - SQL for Data Analysis `Lesson03`

#### Tags
* Author : AH Uyekita
* Title  : _SQL Subqueries & Temporary Tables (Advanced)_
* Date   : 17/12/2018
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** [Derek Steer][derek]

[derek]: https://modeanalytics.com

#### Exercises

All exercises of this chapter I have stored in the Mode Analytics platform.

[Solutions in Mode Analytics][sol_ma]

[sol_ma]: https://modeanalytics.com/ah_uyekita/reports/c44f93e9f2d4

********************************************************************************

## Subqueries

This is a way to nest queries, it means: The result of one query will be used as FROM to the next query.

```sql
SELECT *
FROM(SELECT something
     FROM   interesting) AS table_1
```
In the example above, I have one query nested to another. Bear in mind, I must give a alias to the nested query.

If the result of the subquery is a single value, you are allowed to insert this subquery wherever you want.

## WITH

Also known as _Common Table Expression_ (CTE), is a kinf of subquery but could be more helpful if someone is going to read the code. Due to the possibility to write the code in fragments an assign name, this is very handy.

**Example**
```sql
WITH my_with_example AS (SELECT ... MY CODE)

SELECT something
FROM my_with_example
```
As you can see it provide a better way to code because the code became more readable.
