## Let's create views and synonyms for frequently used attributes and requested queries to optimize script readability, reusability, abstraction, and consistency.

## Views 

This view is for returning data on films that are unavailable due to unreturned rental inventory.
````sql
CREATE VIEW title_unavail AS
SELECT v.title, d.media_id
FROM media d
JOIN movies v ON d.title_id = v.title_id
JOIN rental_history r ON d.media_id = r.media_id
WHERE r.return_date IS NULL;
````

## Synonyms
````sql
CREATE SYNONYM t_u 
FOR title_unavail;
````
