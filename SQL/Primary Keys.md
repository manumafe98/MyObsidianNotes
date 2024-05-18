
A primary key is a unique identifier for a table row. It enforces data integrity by ensuring no two rows have the same value for the primary key column(s). Each table should ideally have a primary key.

Example:

```sql
CREATE TABLE Genre ( 
	genre_id INT PRIMARY KEY, 
	genre VARCHAR(50) NOT NULL 
);
```
