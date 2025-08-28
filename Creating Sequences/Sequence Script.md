## As the film retailer's customer base grows, it would be fitting to automate unique row identifier values.

We can accomplish this by creating sequences for the primary keys of tables: Customer, Movies, Media, Actors.

````sql
CREATE SEQUENCE customer_id
INCREMENT BY 1
START WITH 101
NOMAXVALUE;

CREATE SEQUENCE title_id
START WITH 1
INCREMENT BY 1;

CREATE SEQUENCE media_id
START WITH 1
INCREMENT BY 1;

CREATE SEQUENCE actor_id
START WITH 1
INCREMENT BY 1;
````
