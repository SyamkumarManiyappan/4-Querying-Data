# 4-Querying-Data
SQL Commands - Querying Data

## Insert 10 rows into both tables, as given below. 
Create a table named Country with fields: Id Country_name Population Area Create another table named Persons with fields: Id Fname Lname Population Rating Country_Id Country_name
(1)List the distinct country names from the Persons table. 
(2)Select first names and last names from the Persons table with aliases.
(3)Find all persons with a rating greater than 4.0.
(4)Find countries with a population greater than 10 lakhs. 
(5)Find persons who are from 'USA' or have a rating greater than 4.5. 
(6)Find all persons where the country name is NULL.
(7)Find all persons from the countries 'USA', 'Canada', and 'UK'.
(8)Find all persons not from the countries 'India' and 'Australia'. 
(9)Find all countries with a population between 5 lakhs and 20 lakhs.
(10)Find all countries whose names do not start with 'C'.

Answer : 

Create database Country_And_Polulation;
use  Country_And_Polulation;
--  Create a table named Country with fields: Id, Country_name, Population_Area 

create table Country ( ID int primary Key, Country_name varchar(20) not null, Population int ,Area int );
-- Create another table named Persons with fields: Id Fname Lname Population Rating Country_Id Country_name

Create Table Persons ( ID int , F_name varchar (20) not null ,  Lname varchar (20) , Population int , Rating int,  Country_Id int ,Country_name varchar (20), foreign key (Country_Id) references Country(ID));

insert into Country(ID, Country_name,Population,Area) values 

(1,'India',1420000000,3287000),
(2,'USA',331000000,9834000),
(3,'UAE',83200000,357022),
(4,'Oman',25600000,3287000),
(5,'Lanka',1428700000,987000),
(6,'China',1444216107,9597000),
(7,'Canada',38000000,9985000),
(8,'Japan',213000000,377975),
(9,'Brazil',67000000,8516000),
(10,'UK',67000000,243610);

insert into Persons ( ID , F_name ,  Lname, Population, Rating,  Country_Id ,Country_name) values
(1,'Sharon','Pindi',331000000, 4,2,'India'),
(2,'Karthika','Nelath',38765890, 5,3,'USA'),
(3,'Giri','Krishna',331000000, 5,5,'UAE'),
(4,'Surya','Kumar',35640000, 3,7,'Oman'),
(5,'Sam','John',331087000, 9,6,'Lanka'),
(6,'Hari','Murali',201000000, 4,2,'China'),
(7,'Prathap','Chandra',101000000, 3,7,'Canada'),
(8,'Manu','Manohar',671000000, 4,8,'Australia'),
(9,'Sree','Kala',381000000, 3,10,'Brazil'),
(10,'Krish','Lol',121000000, 5,1,'UK');

-- List the distinct country names from the Persons table.
select distinct Country_name from persons;

-- Select first names and last names from the Persons table with aliases.
select F_name as First_Name , Lname  as Last_Name from persons;
-- Find all persons with a rating greater than 4.0.

select * from persons where rating > 4 ;

-- Find countries with a population greater than 10 lakhs.
select * from Country where Population > 1000000;
-- Find persons who are from 'USA' or have a rating greater than 4.5.
Select * from persons where Country_name ='USA' and rating > 4.5;
alter table Persons;
insert into persons ( ID , F_name ,  Lname, Population, Rating,  Country_Id ,Country_name) values
(13,'Jintom','Jose',121000212, 2,3, Null);

-- Find all persons where the country_name is NULL.

Select * from Persons where country_name is Null;

-- Find all persons from the countries 'USA', 'Canada', and 'UK'.

select * from persons where country_name in ('USA','Canada','UK');

-- Find all persons not from the countries 'India' and 'Australia'

select * from persons where country_name not in ('India','Australia');

-- Find all countries with a population between 5 lakhs and 20 lakhs

select * from Country where Population between 500000 and 2000000;
-- Find all countries whose names do not start with 'C'
select * from country where country_name not like '%C';






