## Now let's script some sample data to our database.

**The names and personal information provided are fictional.**

````sql
INSERT INTO MOVIES
  (TITLE_ID, TITLE, DESCRIPTION, RATING, CATEGORY, RELEASE_DATE)
VALUES
  (1, 'The Saw Shank Redemption', 'A banker convicted of uxoricide forms a
  friendship over a quarter century with a hardened convict, while maintaining his
  innocence and trying to remain hopeful through simple compassion.', 'R', 'DRAMA',
  TO_DATE ('1994-11-13', 'YYYY-MM-DD')),

  (2, 'The Godfather', 'The aging patriarch of an organized crime dynasty
  transfers control of his clandestine empire to his reluctant son.', 'R', 'DRAMA',
  TO_DATE ('1972-03-15','YYYY-MM-DD')),

  (3, 'The Dark Knight', 'When the menace known as the Joker wreaks havoc and
  chaos on the people of Gotham, Batman, James Gordon and Harvey Dent must work
  together to put an end to the madness.', 'PG13', 'ACTION', TO_DATE ('2008-07-14',
  'YYYY-MM-DD')),

  (4, 'The Godfather Part II', 'The early life and career of Vito Corleone in
  1920s New York City is portrayed, while his son, Michael, expands and tightens his
  grip on the family crime syndicate.', 'R', 'DRAMA', TO_DATE ('1974-12-12', 'YYYY-
  MM-DD')),

  (5, '12 Angry Men', 'The jury in a New York City murder trial is frustrated by
  a single member whose skeptical caution forces them to more carefully consider the
  evidence before jumping to a hasty verdict.', 'R', 'DRAMA', TO_DATE ('1957-04-13',
  'YYYY-MM-DD')),

  (6, 'Schindlers List', 'In German-occupied Poland during World War II,
  industrialist Oskar Schindler gradually becomes concerned for his Jewish workforce
  after witnessing their persecution by the Nazis.', 'R', 'DRAMA', TO_DATE ('1993-11-
  30', 'YYYY-MM-DD') 
); 

INSERT INTO CUSTOMER
  (CUSTOMER_ID, LAST_NAME, FIRST_NAME, HOME_PHONE, ADDRESS, CITY, STATE, EMAIL,
  CELL_PHONE)
VALUES 
  (11, 'Jefferson', 'George', '8125556116', '1 East West Avenue', 'Austin',
  'TX', '127.gj@gmail.com', NULL),  
  
  (12, 'Least', 'Second', '9995554444', '123 Main Street', 'Indianapolis', 'IN',
  NULL, NULL),  

  (13, 'Dillon', 'Bob', '7635940678', '7 Arvy Street', 'Versailles', 'IN',
  'bd.0678@gmail.com', NULL),  

  (14, 'Potter', 'Harry', '7771117777', '4 Privet Drive', 'London', 'AZ',
  'boywholived@grffindor.com', NULL),  

  (15, 'Snape', 'Severus', '8886541234', '21 Potions Court', 'London', 'TX',
  'hlfbldprnc@slytherin.com', NULL),  

  (16, 'Dumbledore', 'Albus', '9995414567', '14 Hogwarts Tower', 'London', 'MI',
  'headmaster@hogwarts.com', NULL  
);  

INSERT INTO MEDIA  
  (MEDIA_ID, FORMAT, TITLE_ID)  
VALUES  
  (101, 'MP4', 5),  

  (102, 'MP5', 6  
);  

INSERT INTO RENTAL_HISTORY 
  (MEDIA_ID, RENTAL_DATE, CUSTOMER_ID, RETURN_DATE)  
VALUES 
  (101, TO_DATE ('2010-11-11', 'YYYY-MM-DD'), 15, TO_DATE ('2010-11-12', 'YYYY-
  MM-DD')),  

  (102, TO_DATE ('2006-08-15', 'YYYY-MM-DD'), 16, TO_DATE ('2006-09-10', 'YYYY-
  MM-DD')  
);
````
