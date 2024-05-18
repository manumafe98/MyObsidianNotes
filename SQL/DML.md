
DML stands for Data Manipulation Language. It's a subset of [[SQL]] specifically designed to manage the actual data stored within the tables of a relational database. In simpler terms, DML allows you to interact with the content of your database tables.

## INSERT

```sql
INSERT INTO Film (film_id, title, description, year, Rating, genre_id) 
VALUES (4, 'The Lord of the Rings: The Fellowship of the Ring', 'Epic fantasy adventure...', 2001, 8.8, 1);
```

## UPDATE

```sql
UPDATE Film SET description = 'A hilarious whodunit filled with twists and turns...' 
WHERE film_id = 2;
```

## DELETE

```sql
DELETE FROM Actor 
WHERE actor_id = 2;
```
