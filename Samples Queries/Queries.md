# How many customers have created an account?
````sql
SELECT
 distinct(count(customer.customer_id)) AS Customers
FROM
 customer
````
Result:
<img width="713" height="105" alt="image" src="https://github.com/user-attachments/assets/f99912f6-b389-4150-8a75-0f7e944a7e96" />


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
Result:
<img width="716" height="108" alt="image" src="https://github.com/user-attachments/assets/f0380171-a652-49f5-903e-a89e07e38724" />
