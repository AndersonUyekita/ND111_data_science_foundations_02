# ND111 - SQL for Data Analysis `Lesson03`

#### Tags
* Author : AH Uyekita
* Title  : _Data Cleaning (Advanced)_
* Date   : 18/12/2018
* Course : Data Science II - Foundations Nanodegree
    * COD    : ND111
    * **Instructor:** [Derek Steer][derek]

[derek]: https://modeanalytics.com

#### Exercises

All exercises of this chapter I have stored in the Mode Analytics platform.

[Solutions in Mode Analytics][sol_ma]

[sol_ma]: https://modeanalytics.com/ah_uyekita/reports/

********************************************************************************
## Data Cleaning

#### LEFT and RIGHT

It is the same of Excel functions.

```sql
SELECT LEFT(2, something) AS lefty_part_of_simething
FROM interesting
```
The example above will create a new column with the first two, from the left to right, character of something.

```sql
SELECT RIGHT(2, something) AS lefty_part_of_simething
FROM interesting
```
Almost the same, but start from the right to the left.

#### LEN

Returns the string length.

```sql
SELECT LEN(something)
FROM interesting
```

#### POSITION and STRPOS

POSITION will find a pattern in the string and will return the position (from the left to the right).

```sql
SELECT POSITION(',', something) /*Looking for a coma*/
FROM interesting
```

The STRPOS has the same use and same results.

```sql
SELECT STRPOS(something, ',') /*Looking for a coma*/
FROM interesting
```
Both functions are case sensitive.

#### LOWER and UPPER

Converts string into all lower or all upper cases.

```sql
SELECT LOWER(something)
FROM interesting
```
#### CONCAT

Bind/Combine/Concatenate strings (in different) columns into a new column.

**Example 1**
```sql
SELECT CONCAT(first_name, ' ',last_name) AS complete_name /* The ' ' is the space between strings*/
FROM interesting
```
You can use ||.

**Example 2**
```sql
SELECT first_name || ' ' || last_name AS complete_name /* The ' ' is the space between strings*/
FROM interesting
```
#### CAST

CAST allow to convert one type to another.

**Example 1**
```sql
SELECT CAST(year || month || day AS date) AS formatted_date
FROM interesting
```

The same of Example 1, but with a different notation to CAST clause.

**Example 2:**
```sql
SELECT (year || month || day AS date)::date AS formatted_date
FROM interesting
```
CAST is useful to converter strings into numbers or dates.

#### COALESCE

Converts NULL fields into Zero.
