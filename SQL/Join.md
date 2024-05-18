
Join clauses in [[SQL]] are powerful [[DQL]] tools for combining data from multiple tables based on a shared relationship between them. They allow you to retrieve data from related tables in a single query, providing a more comprehensive view of your information.

## Inner Join

The `INNER JOIN` returns rows where there's a match in both tables based on the join condition. Focuses on Matching Data, it selects rows from two tables where the join condition is met, essentially creating an intersection of data from both tables.

```sql
SELECT Film.title, Genre.genre 
FROM Film 
INNER JOIN Genre ON Film.genre_id = Genre.genre_id;
```

## Left Join

The `LEFT JOIN` returns all rows from the left table (specified before LEFT JOIN) and matching rows from the right table based on the join condition. If there's no match in the right table, it fills in missing values (often NULL) for the right table's columns.
Preserves Left Table Data, it ensures all data from the left table is included, even if there's no corresponding data in the right table.

```sql
SELECT Actor.name, Actor.surname, Film.title 
FROM Actor 
LEFT JOIN Actor_Film ON Actor.actor_id = Actor_Film.actor_id 
LEFT JOIN Film ON Actor_Film.film_id = Film.film_id;
```

## Right Join

The `RIGHT JOIN` similar to Left Join, but prioritizes the right table (specified before RIGHT JOIN). It returns all rows from the right table and matching rows from the left table based on the join condition. If there's no match in the left table, it fills in missing values (often NULL) for the left table's columns.
Preserves Right Table Data, it ensures all data from the right table is included, even if there's no corresponding data in the left table.

```sql
SELECT Genre.genre, Film.title 
FROM Genre 
RIGHT JOIN Film ON Genre.genre_id = Film.genre_id;
```
