
A foreign key is a column (or set of columns) in one table that references the [[Primary Keys|primary key]] of another table. It establishes a link between the two tables, enforcing a specific relationship.

Example:

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

