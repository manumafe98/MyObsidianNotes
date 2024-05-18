
Aggregate functions in [[SQL]] are powerful [[DQL]] tools that allow you to perform calculations on entire groups of data within a table. They condense information about multiple rows into a single summarized value.

## MAX

```sql
SELECT MAX(rating) AS best_rated 
FROM Film;
```

## COUNT

```sql
SELECT COUNT(*) AS films_above_8 
FROM Film 
WHERE rating > 8;
```

## SUM

```sql
SELECT SUM(duration) AS total_duration_minutes 
FROM Film 
WHERE duration IS NOT NULL;
```

## AVG

```sql
SELECT AVG(rating) AS average_rating 
FROM Film;
```


