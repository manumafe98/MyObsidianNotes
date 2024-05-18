
A junction table is a separate table used to represent a [[Relationships#Many to Many|many-to-many]] relationship between two other tables. It contains [[Foreign Keys|foreign keys]] referencing the [[Primary Keys|primary keys]] of both tables, establishing the connections.

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

CREATE TABLE Actor ( 
	actor_id INT PRIMARY KEY, 
	name VARCHAR(50) NOT NULL, 
	surname VARCHAR(50) NOT NULL 
); 

 -- Junction table
CREATE TABLE Actor_Film ( 
	actor_id INT FOREIGN KEY REFERENCES Actor(actor_id), 
	film_id INT FOREIGN KEY REFERENCES Film(film_id), 
	PRIMARY KEY (actor_id, film_id) 
);
```
