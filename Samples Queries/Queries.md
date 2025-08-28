# How many customers have created an account?
````sql
SELECT
 distinct(count(customer.customer_id)) AS Customers
FROM
 customer
````

# How many customers have rented a film?
````sql
SELECT
 distinct(count(rental_history.customer_id)) AS Customers 
FROM
 rental_history
INNER JOIN
 media
ON rental_history.media_id = media.media_id
````
