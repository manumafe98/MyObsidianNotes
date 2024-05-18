
The `GROUP BY` clause is a fundamental [[DQL]] tool in [[SQL]] that allows you to categorize and summarize data based on shared values in one or more columns. It organizes rows with similar characteristics into groups for further analysis using [[Aggregate Functions|aggregate functions]].

**Here's how `GROUP BY` works:**

- You typically start by selecting the columns you want to retrieve from your table.
- Then you use the `GROUP BY` clause to specify the column(s) by which you want to group the rows. All rows that share the same value(s) in the specified column(s) are placed into the same group.

```sql
SELECT year, COUNT(*) AS film_count 
FROM Film 
GROUP BY year;
```

## HAVING

The `HAVING` clause in [[SQL]] is a powerful tool used in conjunction with the `GROUP BY` clause to filter groups of data based on the results of aggregate functions applied to those groups. It allows you to refine your analysis by specifying additional conditions that the summarized values within each group must meet to be included in the final results.

```sql
SELECT year, COUNT(*) AS film_count 
FROM Film 
GROUP BY year 
HAVING COUNT(*) > 10; -- Show years with more than 10 films
```

### WHERE vs. HAVING

Both [[SELECT#WHERE|WHERE]] and `HAVING` clauses filter data in SQL, but they target data at different stages of the query process and serve distinct purposes:

**WHERE Clause:**

- **Function:** Filters individual rows based on column values.
- **Applied Before Grouping:** The `WHERE` clause is used before `GROUP BY` (if present). It filters rows that don't meet the specified criteria, excluding them from further processing.
- **Focuses on Individual Values:** It allows you to select rows based on conditions applied to specific column values within each row.

**HAVING Clause:**

- **Function:** Filters groups of data based on aggregate function results.
- **Applied After Grouping:** The `HAVING` clause is used in conjunction with `GROUP BY`. It filters groups based on the results of aggregate functions applied to those groups.
- **Focuses on Summarized Values:** It allows you to refine your analysis by specifying conditions that the summarized values (count, sum, average, etc.) for each group must meet to be included in the final results.
