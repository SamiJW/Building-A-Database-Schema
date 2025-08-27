# Film-Retailer-Schema
Let's build a schema for a film retailer

# Create Tables 

CREATE TABLE CUSTOMER ( <br/>
CUSTOMER_ID NUMBER (10) NOT NULL, <br/>
LAST_NAME VARCHAR2 (25) NOT NULL, <br/>
FIRST_NAME VARCHAR2 (25) NOT NULL, <br/>
HOME_PHONE VARCHAR2 (12) NOT NULL, <br/>
ADDRESS VARCHAR2 (100) NOT NULL, <br/>
CITY VARCHAR2 (30) NOT NULL, <br/>
STATE VARCHAR2 (2) NOT NULL, <br/>
EMAIL VARCHAR2 (25), <br/>
CELL_PHONE VARCHAR2 (12) <br/>
); <br/>
CREATE TABLE ACTORS ( <br/>
ACTOR_ID NUMBER (10) NOT NULL, <br/>
STAGE_NAME VARCHAR2 (40) NOT NULL, <br/>
FIRST_NAME VARCHAR2 (25) NOT NULL, <br/>
LAST_NAME VARCHAR2 (25) NOT NULL, <br/>
BIRTH_DATE DATE NOT NULL <br/>
); <br/>
CREATE TABLE MOVIES ( <br/>
TITLE_ID NUMBER (10) NOT NULL, <br/>
TITLE VARCHAR2 (60) NOT NULL, <br/>
DESCRIPTION VARCHAR2 (400) NOT NULL, <br/>
RATING VARCHAR2 (4), <br/>
CATEGORY VARCHAR2 (20), <br/>
RELEASE_DATE DATE NOT NULL <br/>
); <br/>
CREATE TABLE STAR_BILLINGS ( <br/>
ACTOR_ID NUMBER (10) NOT NULL, <br/>
TITLE_ID NUMBER (10) NOT NULL, <br/>
"COMMENTS" VARCHAR2 (40) <br/>
); <br/>
CREATE TABLE MEDIA ( <br/>
MEDIA_ID NUMBER (10) NOT NULL, <br/>
FORMAT VARCHAR2 (3) NOT NULL, <br/>
TITLE_ID NUMBER (10) NOT NULL <br/>
); <br/>
CREATE TABLE RENTAL_HISTORY ( <br/>
MEDIA_ID NUMBER (10) NOT NULL, <br/>
RENTAL_DATE DATE NOT NULL, <br/>
CUSTOMER_ID NUMBER (10) NOT NULL, <br/>
RETURN_DATE DATE <br/>
); <br/>

# Set Table Constraints

ALTER TABLE CUSTOMER ADD CONSTRAINT PK_CUSTOMER PRIMARY KEY (CUSTOMER_ID); <br/>
ALTER TABLE ACTORS ADD CONSTRAINT PK_ACTORS PRIMARY KEY (ACTOR_ID); <br/>
ALTER TABLE MOVIES ADD CONSTRAINT PK_MOVIES PRIMARY KEY (TITLE_ID); <br/>
ALTER TABLE STAR_BILLINGS ADD CONSTRAINT PK_STAR_BILLINGS PRIMARY KEY (ACTOR_ID, TITLE_ID); <br/>
ALTER TABLE MEDIA ADD CONSTRAINT PK_MEDIA PRIMARY KEY (MEDIA_ID); <br/>
ALTER TABLE RENTAL_HISTORY ADD CONSTRAINT PK_RENTAL_HISTORY PRIMARY KEY (MEDIA_ID, RENTAL_DATE); <br/>
ALTER TABLE RENTAL_HISTORY ADD CONSTRAINT FK_RENT_MEDIA FOREIGN KEY (MEDIA_ID) REFERENCES MEDIA (MEDIA_ID); <br/>
ALTER TABLE RENTAL_HISTORY ADD CONSTRAINT FK_RENT_CUST FOREIGN KEY (CUSTOMER_ID) REFERENCES CUSTOMER (CUSTOMER_ID); <br/>
ALTER TABLE STAR_BILLINGS ADD CONSTRAINT FK_SB_ACT FOREIGN KEY (ACTOR_ID) REFERENCES ACTORS (ACTOR_ID); <br/>
ALTER TABLE STAR_BILLINGS ADD CONSTRAINT FK_SB_MOV FOREIGN KEY (TITLE_ID) REFERENCES MOVIES (TITLE_ID); <br/>
ALTER TABLE MOVIES ADD CONSTRAINT CK_RATE CHECK (RATING IN ('G', 'PG', 'R', 'PG13')); <br/>
ALTER TABLE MOVIES ADD CONSTRAINT CK_CAT CHECK (CATEGORY IN ('DRAMA', 'COMEDY', 'ACTION', 'CHILD', 'SCIFI', 'DOCUMENTARY')); <br/>

# Insert Table Data

--This is sample data. The names and personal information provided are fictional.

INSERT INTO MOVIES ( <br/>
TITLE_ID, TITLE, DESCRIPTION, RATING, CATEGORY, RELEASE_DATE) <br/>
VALUES ( <br/>
1, 'The Saw Shank Redemption', 'A banker convicted of uxoricide forms a
friendship over a quarter century with a hardened convict, while maintaining his
innocence and trying to remain hopeful through simple compassion.', 'R', 'DRAMA',
TO_DATE ('1994-11-13', 'YYYY-MM-DD') <br/>
); <br/>
INSERT INTO MOVIES ( <br/>
TITLE_ID, TITLE, DESCRIPTION, RATING, CATEGORY, RELEASE_DATE) <br/>
VALUES ( <br/>
2, 'The Godfather', 'The aging patriarch of an organized crime dynasty
transfers control of his clandestine empire to his reluctant son.', 'R', 'DRAMA',
TO_DATE ('1972-03-15','YYYY-MM-DD') <br/>
); <br/>
INSERT INTO MOVIES ( <br/>
TITLE_ID, TITLE, DESCRIPTION, RATING, CATEGORY, RELEASE_DATE) <br/>
VALUES ( <br/>
3, 'The Dark Knight', 'When the menace known as the Joker wreaks havoc and
chaos on the people of Gotham, Batman, James Gordon and Harvey Dent must work
together to put an end to the madness.', 'PG13', 'ACTION', TO_DATE ('2008-07-14',
'YYYY-MM-DD') <br/>
); <br/>
INSERT INTO MOVIES ( <br/>
TITLE_ID, TITLE, DESCRIPTION, RATING, CATEGORY, RELEASE_DATE) <br/>
VALUES ( <br/>
4, 'The Godfather Part II', 'The early life and career of Vito Corleone in
1920s New York City is portrayed, while his son, Michael, expands and tightens his
grip on the family crime syndicate.', 'R', 'DRAMA', TO_DATE ('1974-12-12', 'YYYY-
MM-DD') <br/>
); <br/>
INSERT INTO MOVIES ( <br/>
TITLE_ID, TITLE, DESCRIPTION, RATING, CATEGORY, RELEASE_DATE) <br/>
VALUES ( <br/>
5, '12 Angry Men', 'The jury in a New York City murder trial is frustrated by
a single member whose skeptical caution forces them to more carefully consider the
evidence before jumping to a hasty verdict.', 'R', 'DRAMA', TO_DATE ('1957-04-13',
'YYYY-MM-DD') <br/>
); <br/>
INSERT INTO MOVIES ( <br/>
TITLE_ID, TITLE, DESCRIPTION, RATING, CATEGORY, RELEASE_DATE) <br/>
VALUES ( <br/>
6, 'Schindlers List', 'In German-occupied Poland during World War II,
industrialist Oskar Schindler gradually becomes concerned for his Jewish workforce
after witnessing their persecution by the Nazis.', 'R', 'DRAMA', TO_DATE ('1993-11-
30', 'YYYY-MM-DD') <br/>
); <br/>
INSERT INTO CUSTOMER ( <br/>
CUSTOMER_ID, LAST_NAME, FIRST_NAME, HOME_PHONE, ADDRESS, CITY, STATE, EMAIL,
CELL_PHONE) <br/>
VALUES ( <br/>
11, 'Jefferson', 'George', '8125556116', '1 East West Avenue', 'Austin',
'TX', '127.gj@gmail.com', NULL <br/>
); <br/>
INSERT INTO CUSTOMER ( <br/>
CUSTOMER_ID, LAST_NAME, FIRST_NAME, HOME_PHONE, ADDRESS, CITY, STATE, EMAIL,
CELL_PHONE) <br/>
VALUES ( <br/>
12, 'Least', 'Second', '9995554444', '123 Main Street', 'Indianapolis', 'IN',
NULL, NULL <br/>
); <br/>
INSERT INTO CUSTOMER ( <br/>
CUSTOMER_ID, LAST_NAME, FIRST_NAME, HOME_PHONE, ADDRESS, CITY, STATE, EMAIL,
CELL_PHONE) <br/>
VALUES ( <br/>
13, 'Dillon', 'Bob', '7635940678', '7 Arvy Street', 'Versailles', 'IN',
'bd.0678@gmail.com', NULL <br/>
); <br/>
INSERT INTO CUSTOMER ( <br/>
CUSTOMER_ID, LAST_NAME, FIRST_NAME, HOME_PHONE, ADDRESS, CITY, STATE, EMAIL,
CELL_PHONE) <br/>
VALUES ( <br/>
14, 'Potter', 'Harry', '7771117777', '4 Privet Drive', 'London', 'AZ',
'boywholived@grffindor.com', NULL <br/>
); <br/>
INSERT INTO CUSTOMER ( <br/>
CUSTOMER_ID, LAST_NAME, FIRST_NAME, HOME_PHONE, ADDRESS, CITY, STATE, EMAIL,
CELL_PHONE) <br/>
VALUES ( <br/>
15, 'Snape', 'Severus', '8886541234', '21 Potions Court', 'London', 'TX',
'hlfbldprnc@slytherin.com', NULL <br/>
); <br/>
INSERT INTO CUSTOMER ( <br/>
CUSTOMER_ID, LAST_NAME, FIRST_NAME, HOME_PHONE, ADDRESS, CITY, STATE, EMAIL,
CELL_PHONE) <br/>
VALUES ( <br/>
16, 'Dumbledore', 'Albus', '9995414567', '14 Hogwarts Tower', 'London', 'MI',
'headmaster@hogwarts.com', NULL <br/>
); <br/>
INSERT INTO MEDIA ( <br/>
MEDIA_ID, FORMAT, TITLE_ID) <br/>
VALUES ( <br/>
101, 'MP4', 5 <br/>
); <br/>
INSERT INTO MEDIA ( <br/>
MEDIA_ID, FORMAT, TITLE_ID) <br/>
VALUES ( <br/>
102, 'MP5', 6 <br/>
); <br/>
INSERT INTO RENTAL_HISTORY ( <br/>
MEDIA_ID, RENTAL_DATE, CUSTOMER_ID, RETURN_DATE) <br/>
VALUES ( <br/>
101, TO_DATE ('2010-11-11', 'YYYY-MM-DD'), 15, TO_DATE ('2010-11-12', 'YYYY-
MM-DD') <br/>
); <br/>
INSERT INTO RENTAL_HISTORY ( <br/>
MEDIA_ID, RENTAL_DATE, CUSTOMER_ID, RETURN_DATE) <br/>
VALUES ( <br/>
102, TO_DATE ('2006-08-15', 'YYYY-MM-DD'), 16, TO_DATE ('2006-09-10', 'YYYY-
MM-DD') <br/>
);
