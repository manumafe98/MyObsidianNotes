is the cornerstone of the [[DQL]] portion of [[SQL]], it allows you to retrieve specific data from your database tables. For more in-depth clauses and functions go to the following [doc](https://www.javatpoint.com/sql-select-distinct)

```sql
SELECT * FROM Film;
```

## WHERE

The ``WHERE`` clause acts like a filter in your SQL queries. It allows you to specify conditions that the data in your table(s) must meet to be included in the results.

```sql
SELECT * FROM Film 
WHERE year > 2000;
```

#### IN

The `IN` operator allows you to filter data based on a list of values within a single column.

```sql
SELECT title 
FROM Film 
WHERE genre_id IN (1, 2);
```

#### BETWEEN

The `BETWEEN` operator is useful for filtering data within a specific range.

```sql
SELECT name, surname 
FROM Actor 
WHERE year BETWEEN 1960 AND 1970;
```

#### LIKE

The `LIKE` operator combined with wildcards allows for pattern matching in text searches, working similar as `regex`.

```sql
SELECT title 
FROM Film 
WHERE title LIKE '%Cast Away%';
```

The `%` wildcard matches any sequence of characters.

## LIMIT AND OFFSET

``LIMIT`` and ``OFFSET`` are useful tools for controlling the number of rows returned by your SQL queries, particularly when dealing with large datasets.

The `Limit` purpose is to specify the maximum number of rows you want to retrieve from the result set

```sql
SELECT title 
FROM Film 
LIMIT 5;
```

The `OFFSET` purpose in contrary is to skip a specified number of rows before starting to return results.

```sql
SELECT title 
FROM Film 
LIMIT 5 OFFSET 10;
```

So the previous example will return 5 rows after the row 10.

## ORDER BY

`ORDER BY` sorts the results based on the values in a specific column.

```sql
SELECT title, year 
FROM Film 
ORDER BY year;
```

If you do not specify the order by default is `ASC` (ascending)

Here there is a `DESC` (descending) example:

```sql
SELECT title, year 
FROM Film
ORDER BY year DESC;
```

You can also sort by multiple columns.

