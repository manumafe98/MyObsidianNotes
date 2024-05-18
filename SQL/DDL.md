
DDL stands for Data Definition Language. It's a subset of [[SQL]] specifically designed to define and manipulate the structure of objects in a relational database. Think of it as the blueprint for your database.

## CREATE

Here are a couple of `CREATE` examples:

```sql
CREATE DATABASE Netflix;
```

```sql
CREATE TABLE Film ( 
	film_id INT PRIMARY KEY, 
	title VARCHAR(50) NOT NULL, 
	description TEXT, 
	year INT, 
	rating DECIMAL(1,10),
	duration SMALLINT,
	genre_id INT FOREIGN KEY REFERENCES Genre(genre_id)
);
```

## DROP

You can use `DROP` to delete something in the structure.

```sql
DROP TABLE Actor_Film;
```

## ALTER

You can use `ALTER` to modify the structure.

```sql
ALTER TABLE Film 
ALTER COLUMN year SET DATA TYPE SMALLINT;
```
