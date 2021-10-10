Notes taken from
https://www.w3schools.com/sql
https://www.linkedin.com/learning/learning-sql-programming

# SQL Statements

This document provides a list of SQL statements used in the course _Learning SQL Programming_ from LinkedIn Learning.

Note that this list contains statements which are improper (they have syntax errors) and statements which are incorrect (they do not achieve the desired goal).

## 00_02

```SQL
SELECT * FROM people;
```

```SQL
SELECT first_name FROM people;
```

## 01_01

```SQL
SELECT 'Hello, World!';
```

```SQL
SELECT first_name FROM people;
```

```SQL
SELECT last_name FROM people;
```

```SQL
SELECT first_name, last_name FROM people;
```

```SQL
SELECT last_name, first_name FROM people;
```

```SQL
SELECT * FROM people;
```

```SQL
SELECT first_name, state_code, company FROM people;
```

```SQL
SELECT company, first_name, quiz_points FROM people;
```

## 01_02

```SQL
SELECT * FROM people WHERE state_code='CA';
```

```SQL
SELECT * FROM people WHERE state_code='ca';
```

```SQL
SELECT * FROM people WHERE state_code='FL';
```

```SQL
SELECT * FROM people WHERE state_code='WA';
```

```SQL
SELECT * FROM people WHERE state_code='NY';
```

```SQL
SELECT * FROM people WHERE shirt_or_hat='shirt';
```

```SQL
SELECT first_name, last_name FROM people WHERE shirt_or_hat='shirt';
```

```SQL
SELECT first_name, last, name, shirt_or_hat
FROM people
WHERE
shirt_or_hat='shirt';
```

```SQL
/* Improper Statement */
WHERE shirt_or_hat='shirt'
FROM people
SELECT first_name, last_name, shirt_or_hat;
```

```SQL
/* Improper Statement */
FROM people
SELECT first_name, last_name, shirt_or_hat
WHERE shirt_or_hat='shirt';
```

## 01_03

```SQL
SELECT * FROM Customers
WHERE Country='Mexico';

SELECT * FROM Customers
WHERE CustomerID=1; también se pueden usar operators en where clause

SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;

SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;

SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;

SELECT * FROM Customers
WHERE Country='Germany' AND (City='Berlin' OR City='München');

SELECT * FROM Customers
WHERE NOT Country='Germany' AND NOT Country='USA';
```

```SQL
SELECT first_name, last_name FROM people WHERE state_code='CA' AND shirt_or_hat='shirt';
```

```SQL
SELECT team, first_name, last_name FROM people WHERE state_code='CA' AND shirt_or_hat='shirt' AND team='Angry Ants';
```

```SQL
SELECT team, first_name, last_name FROM people WHERE state_code='CA' AND shirt_or_hat='shirt' AND team!='Angry Ants';
```

```SQL
SELECT team, first_name, last_name FROM people WHERE state_code='CA' AND shirt_or_hat='shirt' AND team IS 'Angry Ants';
```

```SQL
SELECT team, first_name, last_name FROM people WHERE state_code='CA' AND shirt_or_hat='shirt' AND team IS NOT 'Angry Ants';
```

```SQL
SELECT team, first_name, last_name FROM people WHERE state_code='CA' AND shirt_or_hat='shirt' AND team <> 'Angry Ants';
```

```SQL
SELECT team, first_name, last_name FROM people WHERE state_code='CA' OR state_code='CO' AND shirt_or_hat='shirt' AND team IS 'Angry Ants';
```

```SQL
SELECT team, first_name, last_name, shirt_or_hat, state_code FROM people WHERE state_code='CA' OR state_code='CO' AND shirt_or_hat='shirt' AND team IS 'Angry Ants';
```

```SQL
SELECT team, first_name, last_name, shirt_or_hat, state_code FROM people WHERE (state_code='CA' OR state_code='CO') AND shirt_or_hat='shirt' AND team IS 'Angry Ants';
```

```SQL
SELECT team, first_name, last_name, shirt_or_hat, state_code FROM people WHERE state_code='CA' OR (state_code='CO' AND shirt_or_hat='shirt') AND team IS 'Angry Ants';
```

## 01_04

The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.

LIKE is case-sensitive but ILIKE is case-unsensitive

There are two wildcards often used in conjunction with the LIKE operator:

```sql
The percent sign (%) represents zero, one, or multiple characters
The underscore sign (_) represents one, single character
```

```sql
Note: MS Access uses an asterisk (*) instead of the percent sign (%), and a question mark (?) instead of the underscore (_).
```

The percent sign and the underscore can also be used in combinations!
You can also combine any number of conditions using AND or OR operators.

```sql
LIKE  Operator	                  Description
WHERE CustomerName LIKE 'a%'	  Finds any values that start with "a"
WHERE CustomerName LIKE '%a'	  Finds any values that end with "a"
WHERE CustomerName LIKE '%or%'	  Finds any values that have "or" in any position
WHERE CustomerName LIKE '_r%'	  Finds any values that have "r" in the second position
WHERE CustomerName LIKE 'a_%'	  Finds any values that start with "a" and are at least 2 characters in length
WHERE CustomerName LIKE 'a__%'	  Finds any values that start with "a" and are at least 3 characters in length
WHERE ContactName  LIKE 'a%o'	  Finds any values that start with "a" and ends with "o"
```

```sql
SELECT * FROM Customers
WHERE CustomerName NOT LIKE 'a%';
```

```SQL
SELECT * FROM people WHERE state_code='CA' OR state_code='CO' OR state_code='CT';
```

```SQL
SELECT first_name, last_name, state_Code FROM people WHERE state_code LIKE 'C%';
```

```SQL
SELECT first_name, last_name, state_Code FROM people WHERE first_name LIKE 'A%';
```

```SQL
SELECT first_name, last_name, state_Code FROM people WHERE first_name LIKE 'J%';
```

```SQL
SELECT first_name, last_name, state_Code FROM people WHERE first_name LIKE '%J%';
```

```SQL
SELECT first_name, last_name, state_Code FROM people WHERE first_name LIKE 'b%n';
```

```SQL
SELECT * FROM people WHERE company LIKE '%LLC';
```

```SQL
SELECT * FROM people WHERE company LIKE '%LLC' LIMIT 5;
```

```SQL
SELECT * FROM people WHERE company LIKE '%LLC' LIMIT 10;
```

```SQL
SELECT * FROM people WHERE company LIKE '%LLC' LIMIT 10 OFFSET 5;
```

## 01_05

```SQL
SELECT first_name, last_name FROM people;
```

```SQL
SELECT first_name, last_name FROM people ORDER BY first_name;
```

```SQL
SELECT first_name, last_name FROM people ORDER BY first_name ASC;
```

```SQL
SELECT first_name, last_name FROM people ORDER BY first_name DESC;
```

```SQL
SELECT state_code, last_name, first_name FROM people ORDER BY state_code, last_name;
```

```SQL
SELECT state_code, last_name, first_name FROM people ORDER BY state_code, last_name DESC;
```

## 01_06

```SQL
SELECT first_name FROM people;
```

```SQL
SELECT first_name, LENGTH(first_name) FROM people;
```

```SQL
SELECT DISTINCT(first_name) FROM people;
```

<!-- DISTINCT muestra resultados no repetidos, da igual que haya 1 o 100 -->

```SQL
SELECT DISTINCT(first_name) FROM people ORDER BY first_name;
```

```SQL
SELECT DISTINCT(shirt_or_hat) FROM people;
```

```SQL
SELECT COUNT(*) FROM people WHERE state_code='CA';
```

```SQL
SELECT COUNT(first_name) FROM people WHERE state_code='CA';
```

```SQL
SELECT COUNT(last_name) FROM people WHERE state_code='CA';
```

## 01_08

```SQL
SELECT first_name, last_name, quiz_points, shirt_or_hat, team
FROM people
ORDER BY shirt_or_hat, team;
```

## 02_01

```SQL
SELECT first_name, state_code FROM people;
```

```SQL
SELECT first_name, state_code
FROM people
JOIN states ON people.state_code=states.state_abbrev;
```

```SQL
SELECT people.first_name, people.state_code, states.division
FROM people
JOIN states ON people.state_code = states.state_abbrev;
```

```SQL
SELECT * FROM people JOIN states ON people.state_code=states.state_abbrev;
```

```SQL
SELECT * FROM people
JOIN states ON people.state_code = states.state_abbrev
WHERE people.first_name LIKE 'j%' AND states.region = 'South';
```

```SQL
SELECT people.first_name, states.state_name
FROM people, states
WHERE people.state_code=states.state_abbrev;
```

```SQL
SELECT ppl.first_name, st.state_name
FROM people ppl, states st
WHERE ppl.state_code=st.state_abbrev;
```

## 02_02

Different Types of SQL JOINs
Here are the different types of the JOINs in SQL:

(INNER) JOIN: Returns records that have matching values in both tables
LEFT (OUTER) JOIN: Returns all records from the left table, and the matched records from the right table
RIGHT (OUTER) JOIN: Returns all records from the right table, and the matched records from the left table
FULL (OUTER) JOIN: Returns all records when there is a match in either left or right table

```SQL
-- inner join

SELECT people.first_name, people.last_name, people.state_code, states.state_name
FROM people
JOIN states
ON people.state_code=states.state_abbrev;
```

```SQL
-- inner join

SELECT people.first_name, people.last_name, people.state_code, states.state_name
FROM states
JOIN people
ON people.state_code=states.state_abbrev;
```

JOIN Three Tables

```sql
SELECT Orders.OrderID, Customers.CustomerName, Shippers.ShipperName
FROM ((Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID)
INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID);
```

```SQL
-- outer join

SELECT people.first_name, people.last_name, people.state_code, states.state_name
FROM states
LEFT JOIN people
ON people.state_code=states.state_abbrev;
```

```SQL
-- outer join

SELECT people.first_name, people.last_name, people.state_code, states.state_name
FROM states
RIGHT JOIN people
ON people.state_code=states.state_abbrev;

SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
ORDER BY Orders.OrderID;
```

```SQL
-- outer join

SELECT DISTINCT(people.state_code), states.state_name
FROM states
LEFT JOIN people
ON people.state_code=states.state_abbrev;

SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID
ORDER BY Customers.CustomerName;
```

```SQL
-- outer join, para ambas tablas

SELECT DISTINCT(people.state_code), states.state_name
FROM states
FULL OUTER JOIN people
ON people.state_code=states.state_abbrev
ORDER BY states.state_name;
```

SQL Self Join
A self join is a regular join, but the table is joined with itself.

Self Join Syntax

```sql
SELECT column_name(s)
FROM table1 T1, table1 T2
WHERE condition;
```

```sql
SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2, A.City
FROM Customers A, Customers B
WHERE A.CustomerID <> B.CustomerID
AND A.City = B.City
ORDER BY A.City;
```

```sql
SELECT a.name, a.id, b.name, b.dep_id
FROM employee a
JOIN employee b
on a.id = b.id
AND a.xyz = b.xyz;
```

The SQL UNION Operator
The UNION operator is used to combine the result-set of two or more SELECT statements.

Every SELECT statement within UNION must have the same number of columns
The columns must also have similar data types
The columns in every SELECT statement must also be in the same order

UNION Syntax

```sql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

UNION ALL Syntax

The UNION operator selects only distinct values by default. To allow duplicate values, use UNION ALL:

```sql
SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2;
```

Note: The column names in the result-set are usually equal to the column names in the first SELECT statement.

SQL UNION Example
The following SQL statement returns the cities (only distinct values) from both the "Customers" and the "Suppliers" table:

```sql
SELECT City FROM Customers
UNION
SELECT City FROM Suppliers
ORDER BY City;
```

Note: If some customers or suppliers have the same city, each city will only be listed once, because UNION selects only distinct values. Use UNION ALL to also select duplicate values!

SQL UNION ALL Example
The following SQL statement returns the cities (duplicate values also) from both the "Customers" and the "Suppliers" table:

```sql
SELECT City FROM Customers
UNION ALL
SELECT City FROM Suppliers
ORDER BY City;
```

SQL UNION With WHERE
The following SQL statement returns the German cities (only distinct values) from both the "Customers" and the "Suppliers" table:

```sql
SELECT City, Country FROM Customers
WHERE Country='Germany'
UNION
SELECT City, Country FROM Suppliers
WHERE Country='Germany'
ORDER BY City;
```

SQL UNION ALL With WHERE
The following SQL statement returns the German cities (duplicate values also) from both the "Customers" and the "Suppliers" table:

```sql
SELECT City, Country FROM Customers
WHERE Country='Germany'
UNION ALL
SELECT City, Country FROM Suppliers
WHERE Country='Germany'
ORDER BY City;
```

Another UNION Example
The following SQL statement lists all customers and suppliers:

```sql
SELECT 'Customer' AS Type, ContactName, City, Country
FROM Customers
UNION
SELECT 'Supplier', ContactName, City, Country
FROM Suppliers;
```

Notice the "AS Type" above - it is an alias. SQL Aliases are used to give a table or a column a temporary name. An alias only exists for the duration of the query. So, here we have created a temporary column named "Type", that list whether the contact person is a "Customer" or a "Supplier".

## 02_03

```SQL
/* Incorrect statement */
SELECT first_name, COUNT(first_name) FROM people;
```

```SQL
SELECT first_name, COUNT(first_name)
FROM people
GROUP BY first_name;
```

```SQL
/* Incorrect statement */
SELECT first_name, COUNT(first_name)
FROM people
GROUP BY last_name;
```

```SQL
SELECT last_name, COUNT(last_name)
FROM people
GROUP BY last_name;
```

```SQL
SELECT state_code, COUNT(state_code)
FROM people
GROUP BY state_code;
```

```SQL
/* Incorrect Statement */
SELECT state_code, quiz_points, COUNT(quiz_points)
FROM people
GROUP BY quiz_points
```

```SQL
SELECT state_code, quiz_points, COUNT(quiz_points)
FROM people
GROUP BY state_code, quiz_points
```

## 02_05

```SQL
SELECT states.state_name, COUNT(people.shirt_or_hat)
FROM states
JOIN people ON states.state_abbrev=people.state_code
WHERE people.shirt_or_hat='hat'
GROUP BY people.shirt_or_hat, states.state_name;
```

```SQL
SELECT states.division, people.team, count(people.team)
FROM states
JOIN people ON states.state_abbrev=people.state_code
GROUP BY states.division, people.team;
```

## 03_02

```SQL
SELECT 4+2;
```

```SQL
SELECT 1/3;
```

```SQL
SELECT first_name, quiz_points FROM people WHERE quiz_points > 70;
```

```SQL
SELECT first_name, quiz_points FROM people WHERE quiz_points >= 70;
```

```SQL
SELECT first_name, quiz_points FROM people WHERE quiz_points >= 70 ORDER BY quiz_points;
```

```SQL
SELECT first_name, quiz_points FROM people WHERE quiz_points <= 70 ORDER BY quiz_points;
```

```SQL
SELECT MAX(quiz_points), MIN(quiz_points) FROM people;
```

The MIN() function returns the smallest value of the selected column.

The MAX() function returns the largest value of the selected column.

SELECT MIN(Price) AS SmallestPrice
FROM Products;

La columna se llamará SmallestPrice

```SQL
SELECT SUM(quiz_points) FROM people;
```

```SQL
SELECT team, COUNT(*), SUM(quiz_points), SUM(quiz_points)/COUNT(*) FROM people GROUP BY team;
```

```SQL
SELECT team, COUNT(*), SUM(quiz_points), AVG(quiz_points) FROM people GROUP BY team;
```

```sql
SELECT ROUND(AVG(column), 2) FROM film;
```

esto dice que luego de la coma incluye 2 dígitos y no más

## 03_03

```SQL
/* Improper statement */
SELECT first_name, last_name, quiz_points FROM people WHERE quiz_points=MAX(quiz_points);
```

```SQL
SELECT first_name, last_name, quiz_points FROM people WHERE quiz_points=(SELECT MAX(quiz_points) FROM people);
```

```SQL
SELECT * FROM people WHERE state_code=(SELECT state_abbrev FROM states WHERE state_name='Minnesota');
```

## 03_04

```SQL
SELECT first_name, last_name FROM people;
```

```SQL
SELECT LOWER(first_name), UPPER(last_name) FROM people;
```

```SQL
SELECT LOWER(first_name), SUBSTR(last_name, 1, 5) FROM people;
```

```SQL
SELECT LOWER(first_name), SUBSTR(last_name, 1) FROM people;
```

```SQL
SELECT LOWER(first_name), SUBSTR(last_name, -2) FROM people;
```

```SQL
SELECT REPLACE(first_name, 'a', '-') FROM people;
```

```SQL
-- as char convierte en letras
-- y as int convertiría string en números

SELECT quiz_points FROM people ORDER BY quiz_points;
```

```SQL
SELECT quiz_points FROM people ORDER BY CAST(quiz_points AS CHAR);
```

```SQL
SELECT MAX(CAST(quiz_points AS CHAR)) FROM people;
```

```SQL
SELECT MAX(CAST(quiz_points AS INT)) FROM people;
```

## 03_05

```SQL
SELECT first_name, last_name FROM people;
```

```SQL
SELECT first_name, UPPER(last_name) FROM people;
```

```SQL
SELECT first_name as firstname, UPPER(last_name) as surname FROM people;
```

```SQL
SELECT first_name as firstname, UPPER(last_name) as surname FROM people WHERE firstname='Laura';
```

## 03_07

```SQL
SELECT state_code, max(quiz_points) AS maxpoints, avg(quiz_points) AS avgpts
FROM people
GROUP BY state_code
ORDER BY avgpts DESC;
```

## 04_01

```SQL
INSERT INTO people (first_name) VALUES ('Bob');
```

```SQL
SELECT * FROM people;
```

```SQL
INSERT INTO people
(first_name, last_name, state_code, city, shirt_or_hat)
VALUES
('Mary', 'Hamilton', 'OR', 'Portland', 'hat');
```

```SQL
SELECT * FROM people;
```

```SQL
/* Improper Statement */
INSERT INTO people
(first_name, last_name)
VALUES
('George', 'White'),
('Jenn', 'Smith'),
('Carol');
```

```SQL
INSERT INTO people
(first_name, last_name)
VALUES
('George', 'White'),
('Jenn', 'Smith'),
('Carol', NULL);
```

It is not possible to test for NULL values with comparison operators, such as =, <, or <>.

We will have to use the IS NULL and IS NOT NULL operators instead.

```SQL
SELECT * FROM people;
```

## 04_02

If you omit the WHERE clause, all records in the table will be updated!

```SQL
/* Incorrect Statement */
UPDATE people SET last_name = 'Morrison' WHERE first_name='Carlos';
```

```SQL
SELECT last_name FROM people WHERE first_name='Carlos';
```

```SQL
UPDATE people SET last_name = 'Morrison' WHERE last_name='Morrrison';
```

```SQL
SELECT last_name FROM people WHERE first_name='Carlos' AND city='Houston';
```

```SQL
UPDATE people SET last_name='Morrison'  WHERE first_name='Carlos' AND city='Houston';
```

```SQL
SELECT * FROM people WHERE id_number=175;
```

```SQL
UPDATE people SET last_name='Morrison' WHERE id_number=175;
```

```SQL
SELECT * FROM people;
```

```SQL
SELECT * FROM people WHERE company='Fisher LLC';
```

```SQL
UPDATE people SET company='Megacorp Inc' WHERE company='Fisher LLC';
```

```SQL
SELECT * FROM people WHERE company='Fisher LLC';
```

```SQL
SELECT * FROM people WHERE company='Megacorp Inc';
```

## 04_03

```SQL
/* Incorrect Statement */
DELETE FROM people;
```

If you omit the WHERE clause, all records in the table will be deleted!

```SQL
SELECT * FROM people;
```

```SQL
SELECT * FROM people WHERE id_number=1001;
```

```SQL
DELETE FROM people WHERE id_number=1001;
```

```SQL
SELECT * FROM people;
```

```SQL
SELECT * FROM people WHERE quiz_points IS NULL;
```

```SQL
DELETE FROM people WHERE quiz_points IS NULL;
```

```SQL
SELECT * FROM people;
```

It is possible to delete all rows in a table without deleting the table. This means that the table structure, attributes, and indexes will be intact:
The following SQL statement deletes all rows in the "Customers" table, without deleting the table:

DELETE FROM Customers;

```SQL
INSERT INTO people (first_name, last_name, city, state_code, shirt_or_hat, quiz_points, team, signup, age)
VALUES
("Walter", "St. John", "Buffalo", "NY", "hat", "93", "Baffled Badgers", "2021-01-29", NULL),
("Emerald", "Chou", "Topeka", "KS", "shirt", "92", "Angry Ants", "2021-01-29", 34);
```

```SQL
SELECT * FROM people;
```

```SQL
UPDATE people SET shirt_or_hat='shirt' WHERE first_name='Bonnie' AND last_name='Brooks';
```

```SQL
SELECT * FROM people WHERE first_name='Bonnie' AND last_name='Brooks';
```

```SQL
UPDATE people SET shirt_or_hat='shirt' WHERE first_name='Bonnie' AND last_name='Brooks';
```

```SQL
SELECT * FROM people WHERE first_name='Bonnie' AND last_name='Brooks';
```

```SQL
SELECT * FROM people WHERE first_name='Lois' AND last_name='Hart';
```

```SQL
DELETE FROM people WHERE first_name='Lois' AND last_name='Hart';
```

```SQL
SELECT * FROM people WHERE first_name='Lois';
```

No se puede usar agregate-funcions con WHERE clouse, solamente con HAVING

Siempre que usamos agregate-funcions usamos GROUP BY, van de la mano

En GROUP BY statment siempre van todas las columnas que aparecen en el SELECT statment menos la que tenga algún

In the SELECT statment columns must either have an aggregate function or be in the GROUP BY call

```sql
SELECT company, division, SUM(sales)
FROM finance_table
WHERE division IN ('marketing', 'transport')
HAVING SUM(sales) > 30
GROUP BY company, division
ORDER BY SUM(sales)
LIMIT 5;
```

The GROUP BY statement groups rows that have the same values into summary rows, like "find the number of customers in each country".

The GROUP BY statement is often used with aggregate functions (COUNT(), MAX(), MIN(), SUM(), AVG()) to group the result-set by one or more columns.

```sql
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);
```

```sql
SELECT COUNT(id), country
FROM employee
GROUP BY country;

SELECT COUNT(name), current_city
FROM employee
GROUP BY current_city; lo que se pone en GOUP BY debe estar en el SELECCT clouse

SELECT AVG(salary), club
FROM fifa
GROUP BY club
HAVING AVG(salary) > 1000000;

SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
ORDER BY COUNT(CustomerID) DESC;


SELECT categort_col, AGG(data_col)
FROM table
GROUP BY category_col;
```

The SQL SELECT TOP Clause

The SELECT TOP clause is used to specify the number of records to return.

The SELECT TOP clause is useful on large tables with thousands of records. Returning a large number of records can impact performance.

Note: Not all database systems support the SELECT TOP clause. MySQL supports the LIMIT clause to select a limited number of records, while Oracle uses FETCH FIRST n ROWS ONLY and ROWNUM.

SQL Server / MS Access Syntax:

```sql
SELECT TOP number|percent column_name(s)
FROM table_name
WHERE condition;
```

MySQL Syntax:

```sql
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;
```

Oracle 12 Syntax:

```sql
SELECT column_name(s)
FROM table_name
ORDER BY column_name(s)
FETCH FIRST number ROWS ONLY;
```

Older Oracle Syntax:

```sql
SELECT column_name(s)
FROM table_name
WHERE ROWNUM <= number;
```

Older Oracle Syntax (with ORDER BY):

```sql
SELECT *
FROM (SELECT column_name(s) FROM table_name ORDER BY column_name(s))
WHERE ROWNUM <= number;
```

SQL TOP, LIMIT and FETCH FIRST Examples

The following SQL statement selects the first three records from the "Customers" table (for SQL Server/MS Access):

```sql
SELECT TOP 3 * FROM Customers;
```

The following SQL statement shows the equivalent example for MySQL:

```sql
SELECT * FROM Customers
LIMIT 3;
```

The following SQL statement shows the equivalent example for Oracle:

```sql
SELECT * FROM Customers
FETCH FIRST 3 ROWS ONLY;
```

SQL TOP PERCENT Example

The following SQL statement selects the first 50% of the records from the "Customers" table (for SQL Server/MS Access):

```sql
SELECT TOP 50 PERCENT * FROM Customers;
```

The following SQL statement shows the equivalent example for Oracle:

```sql
SELECT * FROM Customers
FETCH FIRST 50 PERCENT ROWS ONLY;
```

ADD a WHERE CLAUSE

The following SQL statement selects the first three records from the "Customers" table, where the country is "Germany" (for SQL Server/MS Access):

```sql
SELECT TOP 3 * FROM Customers
WHERE Country='Germany';
```

The following SQL statement shows the equivalent example for MySQL:

```sql
SELECT * FROM Customers
WHERE Country='Germany'
LIMIT 3;
```

The following SQL statement shows the equivalent example for Oracle:

```sql
SELECT * FROM Customers
WHERE Country='Germany'
FETCH FIRST 3 ROWS ONLY;
```

A wildcard character is used to substitute one or more characters in a string.
Wildcard characters are used with the LIKE operator. The LIKE operator is used in a WHERE clause to search for a specified pattern in a column.

Wildcard Characters in MS Access

```sql
Symbol	Description	                                                    Example
*	    Represents zero or more characters	                            bl* finds bl, black, blue, and blob
?	    Represents a single character	                                h?t finds hot, hat, and hit
[]	    Represents any single character within the brackets	            h[oa]t finds hot and hat, but not hit
!	    Represents any character not in the brackets	                h[!oa]t finds hit, but not hot and hat
-	    Represents a range of characters	                            c[a-b]t finds cat and cbt
#	    Represents any single numeric character	                        2#5 finds 205, 215, 225, 235, 245, 255, 265, 275, 285, and 295
```

Wildcard Characters in SQL Server

```sql
Symbol	Description	                                                    Example
%	    Represents zero or more characters	                            bl% finds bl, black, blue, and blob
_	    Represents a single character	                                h_t finds hot, hat, and hit
[]	    Represents any single character within the brackets	            h[oa]t finds hot and hat, but not hit
^	    Represents any character not in the brackets	                h[^oa]t finds hit, but not hot and hat
-	    Represents a range of characters	                            c[a-b]t finds cat and cbt
```

```sql
Here are some examples showing different LIKE operators with '%' and '_' wildcards:
```

```sql
LIKE    Operator	                                                Description
WHERE   CustomerName LIKE 'a%'	                                    Finds any values that starts with "a"
WHERE   CustomerName LIKE '%a'	                                    Finds any values that ends with "a"
WHERE   CustomerName LIKE '%or%'	                                Finds any values that have "or" in any position
WHERE   CustomerName LIKE '_r%'	                                    Finds any values that have "r" in the second position
WHERE   CustomerName LIKE 'a__%'	                                Finds any values that starts with "a" and are at least 3 characters in length
WHERE   ContactName  LIKE 'a%o'	                                    Finds any values that starts with "a" and ends with "o"
```

```sql
SELECT * FROM Customers
WHERE City LIKE 'ber%';

SELECT * FROM Customers
WHERE City LIKE '%es%';

SELECT * FROM Customers
WHERE City LIKE '_ondon';

SELECT * FROM Customers
WHERE City LIKE 'L_n_on';

SELECT * FROM Customers
WHERE City LIKE '[bsp]%';

SELECT * FROM Customers
WHERE City LIKE '[a-c]%';

SELECT * FROM Customers
WHERE City NOT LIKE '[bsp]%';

SELECT * FROM Customers
WHERE City LIKE '[!bsp]%';
```

The IN operator allows you to specify multiple values in a WHERE clause.

The IN operator is a shorthand for multiple OR conditions.

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name IN (value1, value2, ...);

SELECT column_name(s)
FROM table_name
WHERE column_name IN (SELECT STATEMENT);
```

The following SQL statement selects all customers that are located in "Germany", "France" or "UK":

```sql
SELECT * FROM Customers
WHERE Country IN ('Germany', 'France', 'UK');
```

The following SQL statement selects all customers that are NOT located in "Germany", "France" or "UK":

```sql
SELECT * FROM Customers
WHERE Country NOT IN ('Germany', 'France', 'UK');
```

The following SQL statement selects all customers that are from the same countries as the suppliers:

```sql
SELECT * FROM Customers
WHERE Country IN (SELECT Country FROM Suppliers);
```

The BETWEEN operator selects values within a given range. The values can be numbers, text, or dates.

The BETWEEN operator is inclusive: begin and end values are included.

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;

SELECT * FROM Products
WHERE Price NOT BETWEEN 10 AND 20;
```

SQL aliases are used to give a table, or a column in a table, a temporary name.

Aliases are often used to make column names more readable.

An alias only exists for the duration of that query.

An alias is created with the AS keyword.

Alias Column Syntax

```sql
SELECT column_name AS alias_name
FROM table_name;
```

The following SQL statement creates two aliases, one for the CustomerID column and one for the CustomerName column:

```sql
SELECT CustomerID AS ID, CustomerName AS Customer
FROM Customers;
```

The following SQL statement creates two aliases, one for the CustomerName column and one for the ContactName column. Note: It requires double quotation marks or square brackets if the alias name contains spaces:

```sql
SELECT CustomerName AS Customer, ContactName AS [Contact Person]
FROM Customers;
```

The following SQL statement creates an alias named "Address" that combine four columns (Address, PostalCode, City and Country):

```sql
SELECT CustomerName, Address + ', ' + PostalCode + ' ' + City + ', ' + Country AS Address
FROM Customers;
```

To get the SQL statement above to work in MySQL use the following:

```sql
SELECT CustomerName, CONCAT(Address,', ',PostalCode,', ',City,', ',Country) AS Address
FROM Customers;
```

Alias Table Syntax

```sql
SELECT column_name(s)
FROM table_name AS alias_name;
```

The following SQL statement selects all the orders from the customer with CustomerID=4 (Around the Horn). We use the "Customers" and "Orders" tables, and give them the table aliases of "c" and "o" respectively (Here we use aliases to make the SQL shorter):

```sql
SELECT o.OrderID, o.OrderDate, c.CustomerName
FROM Customers AS c, Orders AS o
WHERE c.CustomerName='Around the Horn' AND c.CustomerID=o.CustomerID;
```

The following SQL statement is the same as above, but without aliases:

```sql
SELECT Orders.OrderID, Orders.OrderDate, Customers.CustomerName
FROM Customers, Orders
WHERE Customers.CustomerName='Around the Horn' AND Customers.CustomerID=Orders.CustomerID;
```

Aliases can be useful when:

There are more than one table involved in a query
Functions are used in the query
Column names are big or not very readable
Two or more columns are combined together

The SQL HAVING Clause
The HAVING clause was added to SQL because the WHERE keyword cannot be used with aggregate functions.

HAVING Syntax

```sql
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);
```

The following SQL statement lists the number of customers in each country. Only include countries with more than 5 customers:

```sql
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5;
```

The following SQL statement lists the number of customers in each country, sorted high to low (Only include countries with more than 5 customers):

```sql
SELECT COUNT(CustomerID), Country
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5
ORDER BY COUNT(CustomerID) DESC;
```

The following SQL statement lists the employees that have registered more than 10 orders:

```sql
SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders
FROM (Orders
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID)
GROUP BY LastName
HAVING COUNT(Orders.OrderID) > 10;
```

The following SQL statement lists if the employees "Davolio" or "Fuller" have registered more than 25 orders:

```sql
SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders
FROM Orders
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
WHERE LastName = 'Davolio' OR LastName = 'Fuller'
GROUP BY LastName
HAVING COUNT(Orders.OrderID) > 25;
```

The SQL EXISTS Operator
The EXISTS operator is used to test for the existence of any record in a subquery.

The EXISTS operator returns TRUE if the subquery returns one or more records.

EXISTS Syntax

```sql
SELECT column_name(s)
FROM table_name
WHERE EXISTS
(SELECT column_name FROM table_name WHERE condition);
```

The following SQL statement returns TRUE and lists the suppliers with a product price less than 20:

```sql
SELECT SupplierName
FROM Suppliers
WHERE EXISTS (SELECT ProductName FROM Products WHERE Products.SupplierID = Suppliers.supplierID AND Price < 20);
```

The following SQL statement returns TRUE and lists the suppliers with a product price equal to 22:

```sql
SELECT SupplierName
FROM Suppliers
WHERE EXISTS (SELECT ProductName FROM Products WHERE Products.SupplierID = Suppliers.supplierID AND Price = 22);
```

The SQL ANY and ALL Operators
The ANY and ALL operators allow you to perform a comparison between a single column value and a range of other values.

The SQL ANY Operator
The ANY operator:

returns a boolean value as a result
returns TRUE if ANY of the subquery values meet the condition
ANY means that the condition will be true if the operation is true for any of the values in the range.

ANY Syntax

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name operator ANY
  (SELECT column_name
  FROM table_name
  WHERE condition);
```

Note: The operator must be a standard comparison operator (=, <>, !=, >, >=, <, or <=).

The SQL ALL Operator
The ALL operator:

returns a boolean value as a result
returns TRUE if ALL of the subquery values meet the condition
is used with SELECT, WHERE and HAVING statements
ALL means that the condition will be true only if the operation is true for all values in the range.

ALL Syntax With SELECT

```sql
SELECT ALL column_name(s)
FROM table_name
WHERE condition;
```

ALL Syntax With WHERE or HAVING

```sql
SELECT column_name(s)
FROM table_name
WHERE column_name operator ALL
  (SELECT column_name
  FROM table_name
  WHERE condition);
```

Note: The operator must be a standard comparison operator (=, <>, !=, >, >=, <, or <=).

SQL ANY Examples
The following SQL statement lists the ProductName if it finds ANY records in the OrderDetails table has Quantity equal to 10 (this will return TRUE because the Quantity column has some values of 10):

```sql
SELECT ProductName
FROM Products
WHERE ProductID = ANY
  (SELECT ProductID
  FROM OrderDetails
  WHERE Quantity = 10);
```

The following SQL statement lists the ProductName if it finds ANY records in the OrderDetails table has Quantity larger than 99 (this will return TRUE because the Quantity column has some values larger than 99):

```sql
SELECT ProductName
FROM Products
WHERE ProductID = ANY
  (SELECT ProductID
  FROM OrderDetails
  WHERE Quantity > 99);
```

The following SQL statement lists the ProductName if it finds ANY records in the OrderDetails table has Quantity larger than 1000 (this will return FALSE because the Quantity column has no values larger than 1000):

```sql
SELECT ProductName
FROM Products
WHERE ProductID = ANY
  (SELECT ProductID
  FROM OrderDetails
  WHERE Quantity > 1000);
```

SQL ALL Examples
The following SQL statement lists ALL the product names:

```sql
SELECT ALL ProductName
FROM Products
WHERE TRUE;
```

The following SQL statement lists the ProductName if ALL the records in the OrderDetails table has Quantity equal to 10. This will of course return FALSE because the Quantity column has many different values (not only the value of 10):

```sql
SELECT ProductName
FROM Products
WHERE ProductID = ALL
  (SELECT ProductID
  FROM OrderDetails
  WHERE Quantity = 10);
```

The SQL SELECT INTO Statement
The SELECT INTO statement copies data from one table into a new table.

SELECT INTO Syntax
Copy all columns into a new table:

```sql
SELECT *
INTO newtable [IN externaldb]
FROM oldtable
WHERE condition;
```

Copy only some columns into a new table:

```sql
SELECT column1, column2, column3, ...
INTO newtable [IN externaldb]
FROM oldtable
WHERE condition;
```

The new table will be created with the column-names and types as defined in the old table. You can create new column names using the AS clause.

SQL SELECT INTO Examples
The following SQL statement creates a backup copy of Customers:

```sql
SELECT * INTO CustomersBackup2017
FROM Customers;
```

The following SQL statement uses the IN clause to copy the table into a new table in another database:

```sql
SELECT * INTO CustomersBackup2017 IN 'Backup.mdb'
FROM Customers;
```

The following SQL statement copies only a few columns into a new table:

```sql
SELECT CustomerName, ContactName INTO CustomersBackup2017
FROM Customers;
```

The following SQL statement copies only the German customers into a new table:

```sql
SELECT * INTO CustomersGermany
FROM Customers
WHERE Country = 'Germany';
```

The following SQL statement copies data from more than one table into a new table:

```sql
SELECT Customers.CustomerName, Orders.OrderID
INTO CustomersOrderBackup2017
FROM Customers
LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
```

Tip: SELECT INTO can also be used to create a new, empty table using the schema of another. Just add a WHERE clause that causes the query to return no data:

```sql
SELECT * INTO newtable
FROM oldtable
WHERE 1 = 0;
```

The SQL INSERT INTO SELECT Statement
The INSERT INTO SELECT statement copies data from one table and inserts it into another table.

The INSERT INTO SELECT statement requires that the data types in source and target tables matches.

Note: The existing records in the target table are unaffected.

INSERT INTO SELECT Syntax
Copy all columns from one table to another table:

```sql
INSERT INTO table2
SELECT * FROM table1
WHERE condition;
```

Copy only some columns from one table into another table:

```sql
INSERT INTO table2 (column1, column2, column3, ...)
SELECT column1, column2, column3, ...
FROM table1
WHERE condition;
```

SQL INSERT INTO SELECT Examples
The following SQL statement copies "Suppliers" into "Customers" (the columns that are not filled with data, will contain NULL):

```sql
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country FROM Suppliers;
```

The following SQL statement copies "Suppliers" into "Customers" (fill all columns):

```sql
INSERT INTO Customers (CustomerName, ContactName, Address, City, PostalCode, Country)
SELECT SupplierName, ContactName, Address, City, PostalCode, Country FROM Suppliers;
```

The following SQL statement copies only the German suppliers into "Customers":

```sql
INSERT INTO Customers (CustomerName, City, Country)
SELECT SupplierName, City, Country FROM Suppliers
WHERE Country='Germany';
```

The SQL CASE Statement
The CASE statement goes through conditions and returns a value when the first condition is met (like an if-then-else statement). So, once a condition is true, it will stop reading and return the result. If no conditions are true, it returns the value in the ELSE clause.

If there is no ELSE part and no conditions are true, it returns NULL.

CASE Syntax

```sql
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;
```

SQL CASE Examples
The following SQL goes through conditions and returns a value when the first condition is met:

```sql
SELECT OrderID, Quantity,
CASE
    WHEN Quantity > 30 THEN 'The quantity is greater than 30'
    WHEN Quantity = 30 THEN 'The quantity is 30'
    ELSE 'The quantity is under 30'
END AS QuantityText
FROM OrderDetails;
```

The following SQL will order the customers by City. However, if City is NULL, then order by Country:

```sql
SELECT CustomerName, City, Country
FROM Customers
ORDER BY
(CASE
    WHEN City IS NULL THEN Country
    ELSE City
END);
```

SQL NULL Functions
SQL IFNULL(), ISNULL(), COALESCE(), and NVL() Functions

Suppose that the "UnitsOnOrder" column is optional, and may contain NULL values.

Look at the following SELECT statement:

```sql
SELECT ProductName, UnitPrice * (UnitsInStock + UnitsOnOrder)
FROM Products;
```

In the example above, if any of the "UnitsOnOrder" values are NULL, the result will be NULL.

Solutions
MySQL

The MySQL IFNULL() function lets you return an alternative value if an expression is NULL:

```sql
SELECT ProductName, UnitPrice * (UnitsInStock + IFNULL(UnitsOnOrder, 0))
FROM Products;
```

or we can use the COALESCE() function, like this:

```sql
SELECT ProductName, UnitPrice * (UnitsInStock + COALESCE(UnitsOnOrder, 0))
FROM Products;
```

SQL Server

The SQL Server ISNULL() function lets you return an alternative value when an expression is NULL:

```sql
SELECT ProductName, UnitPrice * (UnitsInStock + ISNULL(UnitsOnOrder, 0))
FROM Products;
```

MS Access

The MS Access IsNull() function returns TRUE (-1) if the expression is a null value, otherwise FALSE (0):

```sql
SELECT ProductName, UnitPrice * (UnitsInStock + IIF(IsNull(UnitsOnOrder), 0, UnitsOnOrder))
FROM Products;
```

Oracle

The Oracle NVL() function achieves the same result:

```sql
SELECT ProductName, UnitPrice * (UnitsInStock + NVL(UnitsOnOrder, 0))
FROM Products;
```

SQL Stored Procedures for SQL Server

What is a Stored Procedure?
A stored procedure is a prepared SQL code that you can save, so the code can be reused over and over again.

So if you have an SQL query that you write over and over again, save it as a stored procedure, and then just call it to execute it.

You can also pass parameters to a stored procedure, so that the stored procedure can act based on the parameter value(s) that is passed.

Stored Procedure Syntax

```sql
CREATE PROCEDURE procedure_name
AS
sql_statement
GO;
```

Execute a Stored Procedure

```sql
EXEC procedure_name;
```

Stored Procedure Example
The following SQL statement creates a stored procedure named "SelectAllCustomers" that selects all records from the "Customers" table:

```sql
CREATE PROCEDURE SelectAllCustomers
AS
SELECT * FROM Customers
GO;
```

Execute the stored procedure above as follows:

```sql
EXEC SelectAllCustomers;
```

Stored Procedure With One Parameter

The following SQL statement creates a stored procedure that selects Customers from a particular City from the "Customers" table:

```sql
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30)
AS
SELECT * FROM Customers WHERE City = @City
GO;
```

Execute the stored procedure above as follows:

```sql
EXEC SelectAllCustomers @City = 'London';
```

Stored Procedure With Multiple Parameters

Setting up multiple parameters is very easy. Just list each parameter and the data type separated by a comma as shown below.

The following SQL statement creates a stored procedure that selects Customers from a particular City with a particular PostalCode from the "Customers" table:

```sql
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30), @PostalCode nvarchar(10)
AS
SELECT * FROM Customers WHERE City = @City AND PostalCode = @PostalCode
GO;
```

Execute the stored procedure above as follows:

```sql
EXEC SelectAllCustomers @City = 'London', @PostalCode = 'WA1 1DP';
```

SQL Comments
Comments are used to explain sections of SQL statements, or to prevent execution of SQL statements.

Note: The examples in this chapter will not work in Firefox and Microsoft Edge!

Comments are not supported in Microsoft Access databases. Firefox and Microsoft Edge are using Microsoft Access database in our examples.

Single Line Comments
Single line comments start with --.

Any text between -- and the end of the line will be ignored (will not be executed).

The following example uses a single-line comment as an explanation:

```sql
--Select all:
SELECT * FROM Customers;
```

The following example uses a single-line comment to ignore the end of a line:

```sql
SELECT * FROM Customers -- WHERE City='Berlin';
```

The following example uses a single-line comment to ignore a statement:

```sql
--SELECT * FROM Customers;
SELECT * FROM Products;
```

SQL Arithmetic Operators

```sql
Operator	Description
+	        Add
-	        Subtract
*	        Multiply
/	        Divide
%	        Modulo
```

SQL Bitwise Operators

```sql
Operator	Description
&	        Bitwise AND
|	        Bitwise OR
^	        Bitwise exclusive OR
```

SQL Comparison Operators

```sql
Operator	Description
=	        Equal to
>	        Greater than
<	        Less than
>=	        Greater than or equal to
<=	        Less than or equal to
<>	        Not equal to
```

SQL Compound Operators

```sql
Operator	Description
+=	        Add equals
-=	        Subtract equals
*=	        Multiply equals
/=	        Divide equals
%=	        Modulo equals
&=	        Bitwise AND equals
^-=	        Bitwise exclusive equals
|*=	        itwise OR equals
```

SQL Logical Operators

```sql
Operator	Description
ALL	        TRUE if all of the subquery values meet the condition
AND	        TRUE if all the conditions separated by AND is TRUE
ANY	        TRUE if any of the subquery values meet the condition
BETWEEN	    TRUE if the operand is within the range of comparisons
EXISTS	    TRUE if the subquery returns one or more records
IN	        TRUE if the operand is equal to one of a list of expressions
LIKE	    TRUE if the operand matches a pattern
NOT	        Displays a record if the condition(s) is NOT TRUE
OR	        TRUE if any of the conditions separated by OR is TRUE
SOME	    TRUE if any of the subquery values meet the condition
```

The SQL CREATE DATABASE Statement
The CREATE DATABASE statement is used to create a new SQL database.

Syntax

```sql
CREATE DATABASE databasename;
```

The SQL DROP DATABASE Statement
The DROP DATABASE statement is used to drop an existing SQL database.

Syntax

```sql
DROP DATABASE databasename;
```

The SQL BACKUP DATABASE Statement
The BACKUP DATABASE statement is used in SQL Server to create a full back up of an existing SQL database.

Syntax

```sql
BACKUP DATABASE databasename
TO DISK = 'filepath';
```

The SQL BACKUP WITH DIFFERENTIAL Statement
A differential back up only backs up the parts of the database that have changed since the last full database backup.

Syntax

```sql
BACKUP DATABASE databasename
TO DISK = 'filepath'
WITH DIFFERENTIAL;
```

BACKUP DATABASE Example
The following SQL statement creates a full back up of the existing database "testDB" to the D disk:

```sql
BACKUP DATABASE testDB
TO DISK = 'D:\backups\testDB.bak';
```

BACKUP WITH DIFFERENTIAL Example
The following SQL statement creates a differential back up of the database "testDB":

```sql
BACKUP DATABASE testDB
TO DISK = 'D:\backups\testDB.bak'
WITH DIFFERENTIAL;
```

Tip: A differential back up reduces the back up time (since only the changes are backed up).

The SQL CREATE TABLE Statement
The CREATE TABLE statement is used to create a new table in a database.

Syntax

```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);
```

The column parameters specify the names of the columns of the table.

The datatype parameter specifies the type of data the column can hold (e.g. varchar, integer, date, etc.).

SQL CREATE TABLE Example
The following example creates a table called "Persons" that contains five columns: PersonID, LastName, FirstName, Address, and City:

Example

```sql
CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);
```

The PersonID column is of type int and will hold an integer.

The LastName, FirstName, Address, and City columns are of type varchar and will hold characters, and the maximum length for these fields is 255 characters.

The empty "Persons" table will now look like this:

PersonID LastName FirstName Address City
Tip: The empty "Persons" table can now be filled with data with the SQL INSERT INTO statement.

Create Table Using Another Table

A copy of an existing table can also be created using CREATE TABLE.

The new table gets the same column definitions. All columns or specific columns can be selected.

If you create a new table using an existing table, the new table will be filled with the existing values from the old table.

Syntax

```sql
CREATE TABLE new_table_name AS
    SELECT column1, column2,...
    FROM existing_table_name
    WHERE ....;

```

The following SQL creates a new table called "TestTables" (which is a copy of the "Customers" table):

Example

```sql
CREATE TABLE TestTable AS
SELECT customername, contactname
FROM customers;
```

The SQL DROP TABLE Statement
The DROP TABLE statement is used to drop an existing table in a database.

Syntax

```sql
DROP TABLE table_name;
```

SQL TRUNCATE TABLE
The TRUNCATE TABLE statement is used to delete the data inside a table, but not the table itself.

Syntax

```sql
TRUNCATE TABLE table_name;
```

SQL ALTER TABLE Statement
The ALTER TABLE statement is used to add, delete, or modify columns in an existing table.

The ALTER TABLE statement is also used to add and drop various constraints on an existing table.

ALTER TABLE - ADD Column
To add a column in a table, use the following syntax:

```sql
ALTER TABLE table_name
ADD column_name datatype;
```

The following SQL adds an "Email" column to the "Customers" table:

Example

```sql
ALTER TABLE Customers
ADD Email varchar(255);
```

ALTER TABLE - DROP COLUMN
To delete a column in a table, use the following syntax (notice that some database systems don't allow deleting a column):

```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```

The following SQL deletes the "Email" column from the "Customers" table:

Example

```sql
ALTER TABLE Customers
DROP COLUMN Email;
```

ALTER TABLE - ALTER/MODIFY COLUMN
To change the data type of a column in a table, use the following syntax:

SQL Server / MS Access:

```sql
ALTER TABLE table_name
ALTER COLUMN column_name datatype;
```

My SQL / Oracle (prior version 10G):

```sql
ALTER TABLE table_name
MODIFY COLUMN column_name datatype;
```

Oracle 10G and later:

```sql
ALTER TABLE table_name
MODIFY column_name datatype;
```

SQL constraints are used to specify rules for data in a table.

SQL Create Constraints
Constraints can be specified when the table is created with the CREATE TABLE statement, or after the table is created with the ALTER TABLE statement.

Syntax

```sql
CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    column3 datatype constraint,
    ....
);
```

SQL Constraints
SQL constraints are used to specify rules for the data in a table.

Constraints are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the table. If there is any violation between the constraint and the data action, the action is aborted.

Constraints can be column level or table level. Column level constraints apply to a column, and table level constraints apply to the whole table.

The following constraints are commonly used in SQL:

NOT NULL - Ensures that a column cannot have a NULL value
UNIQUE - Ensures that all values in a column are different
PRIMARY KEY - A combination of a NOT NULL and UNIQUE. Uniquely identifies each row in a table
FOREIGN KEY - Prevents actions that would destroy links between tables
CHECK - Ensures that the values in a column satisfies a specific condition
DEFAULT - Sets a default value for a column if no value is specified
CREATE INDEX - Used to create and retrieve data from the database very quickly

SQL NOT NULL Constraint
By default, a column can hold NULL values.

The NOT NULL constraint enforces a column to NOT accept NULL values.

This enforces a field to always contain a value, which means that you cannot insert a new record, or update a record without adding a value to this field.

SQL NOT NULL on CREATE TABLE
The following SQL ensures that the "ID", "LastName", and "FirstName" columns will NOT accept NULL values when the "Persons" table is created:

Example

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);
```

SQL NOT NULL on ALTER TABLE
To create a NOT NULL constraint on the "Age" column when the "Persons" table is already created, use the following SQL:

```sql
ALTER TABLE Persons
MODIFY Age int NOT NULL;
```

SQL UNIQUE Constraint
The UNIQUE constraint ensures that all values in a column are different.

Both the UNIQUE and PRIMARY KEY constraints provide a guarantee for uniqueness for a column or set of columns.

A PRIMARY KEY constraint automatically has a UNIQUE constraint.

However, you can have many UNIQUE constraints per table, but only one PRIMARY KEY constraint per table.

SQL UNIQUE Constraint on CREATE TABLE
The following SQL creates a UNIQUE constraint on the "ID" column when the "Persons" table is created:

SQL Server / Oracle / MS Access:

```sql
CREATE TABLE Persons (
    ID int NOT NULL UNIQUE,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

MySQL:

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    UNIQUE (ID)
);
```

To name a UNIQUE constraint, and to define a UNIQUE constraint on multiple columns, use the following SQL syntax:

MySQL / SQL Server / Oracle / MS Access:

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT UC_Person UNIQUE (ID,LastName)
);
```

SQL UNIQUE Constraint on ALTER TABLE
To create a UNIQUE constraint on the "ID" column when the table is already created, use the following SQL:

MySQL / SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Persons
ADD UNIQUE (ID);
```

To name a UNIQUE constraint, and to define a UNIQUE constraint on multiple columns, use the following SQL syntax:

MySQL / SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Persons
ADD CONSTRAINT UC_Person UNIQUE (ID,LastName);
```

DROP a UNIQUE Constraint
To drop a UNIQUE constraint, use the following SQL:

MySQL:

```sql
ALTER TABLE Persons
DROP INDEX UC_Person;
```

SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Persons
DROP CONSTRAINT UC_Person;
```

SQL PRIMARY KEY Constraint
The PRIMARY KEY constraint uniquely identifies each record in a table.

Primary keys must contain UNIQUE values, and cannot contain NULL values.

A table can have only ONE primary key; and in the table, this primary key can consist of single or multiple columns (fields).

SQL PRIMARY KEY on CREATE TABLE
The following SQL creates a PRIMARY KEY on the "ID" column when the "Persons" table is created:

MySQL:

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID)
);
```

SQL Server / Oracle / MS Access:

```sql
CREATE TABLE Persons (
    ID int NOT NULL PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

To allow naming of a PRIMARY KEY constraint, and for defining a PRIMARY KEY constraint on multiple columns, use the following SQL syntax:

MySQL / SQL Server / Oracle / MS Access:

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CONSTRAINT PK_Person PRIMARY KEY (ID,LastName)
);
```

Note: In the example above there is only ONE PRIMARY KEY (PK_Person). However, the VALUE of the primary key is made up of TWO COLUMNS (ID + LastName).

SQL PRIMARY KEY on ALTER TABLE
To create a PRIMARY KEY constraint on the "ID" column when the table is already created, use the following SQL:

MySQL / SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Persons
ADD PRIMARY KEY (ID);
```

To allow naming of a PRIMARY KEY constraint, and for defining a PRIMARY KEY constraint on multiple columns, use the following SQL syntax:

MySQL / SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Persons
ADD CONSTRAINT PK_Person PRIMARY KEY (ID,LastName);
```

Note: If you use ALTER TABLE to add a primary key, the primary key column(s) must have been declared to not contain NULL values (when the table was first created).

DROP a PRIMARY KEY Constraint
To drop a PRIMARY KEY constraint, use the following SQL:

MySQL:

```sql
ALTER TABLE Persons
DROP PRIMARY KEY;
```

SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Persons
DROP CONSTRAINT PK_Person;
```

SQL FOREIGN KEY Constraint
The FOREIGN KEY constraint is used to prevent actions that would destroy links between tables.

A FOREIGN KEY is a field (or collection of fields) in one table, that refers to the PRIMARY KEY in another table.

The table with the foreign key is called the child table, and the table with the primary key is called the referenced or parent table.SQL FOREIGN KEY Constraint
The FOREIGN KEY constraint is used to prevent actions that would destroy links between tables.

A FOREIGN KEY is a field (or collection of fields) in one table, that refers to the PRIMARY KEY in another table.

The table with the foreign key is called the child table, and the table with the primary key is called the referenced or parent table.

Notice that the "PersonID" column in the "Orders" table points to the "PersonID" column in the "Persons" table.

The "PersonID" column in the "Persons" table is the PRIMARY KEY in the "Persons" table.

The "PersonID" column in the "Orders" table is a FOREIGN KEY in the "Orders" table.

The FOREIGN KEY constraint prevents invalid data from being inserted into the foreign key column, because it has to be one of the values contained in the parent table.

SQL FOREIGN KEY on CREATE TABLE
The following SQL creates a FOREIGN KEY on the "PersonID" column when the "Orders" table is created:

MySQL:

```sql
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    FOREIGN KEY (PersonID) REFERENCES Persons(PersonID)
);
```

SQL Server / Oracle / MS Access:

```sql
CREATE TABLE Orders (
    OrderID int NOT NULL PRIMARY KEY,
    OrderNumber int NOT NULL,
    PersonID int FOREIGN KEY REFERENCES Persons(PersonID)
);
```

To allow naming of a FOREIGN KEY constraint, and for defining a FOREIGN KEY constraint on multiple columns, use the following SQL syntax:

MySQL / SQL Server / Oracle / MS Access:

```sql
CREATE TABLE Orders (
    OrderID int NOT NULL,
    OrderNumber int NOT NULL,
    PersonID int,
    PRIMARY KEY (OrderID),
    CONSTRAINT FK_PersonOrder FOREIGN KEY (PersonID)
    REFERENCES Persons(PersonID)
);
```

SQL FOREIGN KEY on ALTER TABLE
To create a FOREIGN KEY constraint on the "PersonID" column when the "Orders" table is already created, use the following SQL:

MySQL / SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Orders
ADD FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

To allow naming of a FOREIGN KEY constraint, and for defining a FOREIGN KEY constraint on multiple columns, use the following SQL syntax:

MySQL / SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Orders
ADD CONSTRAINT FK_PersonOrder
FOREIGN KEY (PersonID) REFERENCES Persons(PersonID);
```

DROP a FOREIGN KEY Constraint
To drop a FOREIGN KEY constraint, use the following SQL:

MySQL:

```sql
ALTER TABLE Orders
DROP FOREIGN KEY FK_PersonOrder;
```

SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Orders
DROP CONSTRAINT FK_PersonOrder;
```

SQL CHECK Constraint
The CHECK constraint is used to limit the value range that can be placed in a column.

If you define a CHECK constraint on a column it will allow only certain values for this column.

If you define a CHECK constraint on a table it can limit the values in certain columns based on values in other columns in the row.

SQL CHECK on CREATE TABLE
The following SQL creates a CHECK constraint on the "Age" column when the "Persons" table is created. The CHECK constraint ensures that the age of a person must be 18, or older:

MySQL:

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    CHECK (Age>=18)
);
```

SQL Server / Oracle / MS Access:

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int CHECK (Age>=18)
);
```

To allow naming of a CHECK constraint, and for defining a CHECK constraint on multiple columns, use the following SQL syntax:

MySQL / SQL Server / Oracle / MS Access:

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255),
    CONSTRAINT CHK_Person CHECK (Age>=18 AND City='Sandnes')
);
```

SQL CHECK on ALTER TABLE
To create a CHECK constraint on the "Age" column when the table is already created, use the following SQL:

MySQL / SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Persons
ADD CHECK (Age>=18);
```

To allow naming of a CHECK constraint, and for defining a CHECK constraint on multiple columns, use the following SQL syntax:

MySQL / SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Persons
ADD CONSTRAINT CHK_PersonAge CHECK (Age>=18 AND City='Sandnes');
```

DROP a CHECK Constraint
To drop a CHECK constraint, use the following SQL:

SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Persons
DROP CONSTRAINT CHK_PersonAge;
```

MySQL:

```sql
ALTER TABLE Persons
DROP CHECK CHK_PersonAge;
```

SQL DEFAULT Constraint
The DEFAULT constraint is used to set a default value for a column.

The default value will be added to all new records, if no other value is specified.

SQL DEFAULT on CREATE TABLE
The following SQL sets a DEFAULT value for the "City" column when the "Persons" table is created:

My SQL / SQL Server / Oracle / MS Access:

```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255) DEFAULT 'Sandnes'
);
```

The DEFAULT constraint can also be used to insert system values, by using functions like GETDATE():

```sql
CREATE TABLE Orders (
    ID int NOT NULL,
    OrderNumber int NOT NULL,
    OrderDate date DEFAULT GETDATE()
);
```

SQL DEFAULT on ALTER TABLE
To create a DEFAULT constraint on the "City" column when the table is already created, use the following SQL:

MySQL:

```sql
ALTER TABLE Persons
ALTER City SET DEFAULT 'Sandnes';
```

SQL Server:

```sql
ALTER TABLE Persons
ADD CONSTRAINT df_City
DEFAULT 'Sandnes' FOR City;
```

MS Access:

```sql
ALTER TABLE Persons
ALTER COLUMN City SET DEFAULT 'Sandnes';
```

Oracle:

```sql
ALTER TABLE Persons
MODIFY City DEFAULT 'Sandnes';
```

DROP a DEFAULT Constraint
To drop a DEFAULT constraint, use the following SQL:

MySQL:

```sql
ALTER TABLE Persons
ALTER City DROP DEFAULT;
```

SQL Server / Oracle / MS Access:

```sql
ALTER TABLE Persons
ALTER COLUMN City DROP DEFAULT;
```

SQL CREATE INDEX Statement
The CREATE INDEX statement is used to create indexes in tables.

Indexes are used to retrieve data from the database more quickly than otherwise. The users cannot see the indexes, they are just used to speed up searches/queries.

Note: Updating a table with indexes takes more time than updating a table without (because the indexes also need an update). So, only create indexes on columns that will be frequently searched against.

CREATE INDEX Syntax
Creates an index on a table. Duplicate values are allowed:

```sql
CREATE INDEX index_name
ON table_name (column1, column2, ...);
```

CREATE UNIQUE INDEX Syntax
Creates a unique index on a table. Duplicate values are not allowed:

```sql
CREATE UNIQUE INDEX index_name
ON table_name (column1, column2, ...);
```

Note: The syntax for creating indexes varies among different databases. Therefore: Check the syntax for creating indexes in your database.

CREATE INDEX Example
The SQL statement below creates an index named "idx_lastname" on the "LastName" column in the "Persons" table:

```sql
CREATE INDEX idx_lastname
ON Persons (LastName);
```

If you want to create an index on a combination of columns, you can list the column names within the parentheses, separated by commas:

```sql
CREATE INDEX idx_pname
ON Persons (LastName, FirstName);
```

DROP INDEX Statement
The DROP INDEX statement is used to delete an index in a table.

MS Access:

```sql
DROP INDEX index_name ON table_name;
```

SQL Server:

```sql
DROP INDEX table_name.index_name;
```

DB2/Oracle:

```sql
DROP INDEX index_name;
```

MySQL:

```sql
ALTER TABLE table_name
DROP INDEX index_name;
```

AUTO INCREMENT Field
Auto-increment allows a unique number to be generated automatically when a new record is inserted into a table.

Often this is the primary key field that we would like to be created automatically every time a new record is inserted.

Syntax for MySQL
The following SQL statement defines the "Personid" column to be an auto-increment primary key field in the "Persons" table:

```sql
CREATE TABLE Persons (
    Personid int NOT NULL AUTO_INCREMENT,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (Personid)
);
```

MySQL uses the AUTO_INCREMENT keyword to perform an auto-increment feature.

By default, the starting value for AUTO_INCREMENT is 1, and it will increment by 1 for each new record.

To let the AUTO_INCREMENT sequence start with another value, use the following SQL statement:

```sql
ALTER TABLE Persons AUTO_INCREMENT=100;
```

To insert a new record into the "Persons" table, we will NOT have to specify a value for the "Personid" column (a unique value will be added automatically):

```sql
INSERT INTO Persons (FirstName,LastName)
VALUES ('Lars','Monsen');
```

The SQL statement above would insert a new record into the "Persons" table. The "Personid" column would be assigned a unique value. The "FirstName" column would be set to "Lars" and the "LastName" column would be set to "Monsen".

Syntax for SQL Server
The following SQL statement defines the "Personid" column to be an auto-increment primary key field in the "Persons" table:

```sql
CREATE TABLE Persons (
    Personid int IDENTITY(1,1) PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

The MS SQL Server uses the IDENTITY keyword to perform an auto-increment feature.

In the example above, the starting value for IDENTITY is 1, and it will increment by 1 for each new record.

Tip: To specify that the "Personid" column should start at value 10 and increment by 5, change it to IDENTITY(10,5).

To insert a new record into the "Persons" table, we will NOT have to specify a value for the "Personid" column (a unique value will be added automatically):

```sql
INSERT INTO Persons (FirstName,LastName)
VALUES ('Lars','Monsen');
```

The SQL statement above would insert a new record into the "Persons" table. The "Personid" column would be assigned a unique value. The "FirstName" column would be set to "Lars" and the "LastName" column would be set to "Monsen".

Syntax for Access
The following SQL statement defines the "Personid" column to be an auto-increment primary key field in the "Persons" table:

```sql
CREATE TABLE Persons (
    Personid AUTOINCREMENT PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

The MS Access uses the AUTOINCREMENT keyword to perform an auto-increment feature.

By default, the starting value for AUTOINCREMENT is 1, and it will increment by 1 for each new record.

Tip: To specify that the "Personid" column should start at value 10 and increment by 5, change the autoincrement to AUTOINCREMENT(10,5).

To insert a new record into the "Persons" table, we will NOT have to specify a value for the "Personid" column (a unique value will be added automatically):

```sql
INSERT INTO Persons (FirstName,LastName)
VALUES ('Lars','Monsen');
```

The SQL statement above would insert a new record into the "Persons" table. The "Personid" column would be assigned a unique value. The "FirstName" column would be set to "Lars" and the "LastName" column would be set to "Monsen".

Syntax for Oracle
In Oracle the code is a little bit more tricky.

You will have to create an auto-increment field with the sequence object (this object generates a number sequence).

Use the following CREATE SEQUENCE syntax:

```sql
CREATE SEQUENCE seq_person
MINVALUE 1
START WITH 1
INCREMENT BY 1
CACHE 10;
```

The code above creates a sequence object called seq_person, that starts with 1 and will increment by 1. It will also cache up to 10 values for performance. The cache option specifies how many sequence values will be stored in memory for faster access.

To insert a new record into the "Persons" table, we will have to use the nextval function (this function retrieves the next value from seq_person sequence):

```sql
INSERT INTO Persons (Personid,FirstName,LastName)
VALUES (seq_person.nextval,'Lars','Monsen');
```

The SQL statement above would insert a new record into the "Persons" table. The "Personid" column would be assigned the next number from the seq_person sequence. The "FirstName" column would be set to "Lars" and the "LastName" column would be set to "Monsen".

SQL Dates
The most difficult part when working with dates is to be sure that the format of the date you are trying to insert, matches the format of the date column in the database.

As long as your data contains only the date portion, your queries will work as expected. However, if a time portion is involved, it gets more complicated.

SQL Date Data Types
MySQL comes with the following data types for storing a date or a date/time value in the database:

DATE - format YYYY-MM-DD
DATETIME - format: YYYY-MM-DD HH:MI:SS
TIMESTAMP - format: YYYY-MM-DD HH:MI:SS
YEAR - format YYYY or YY
SQL Server comes with the following data types for storing a date or a date/time value in the database:

DATE - format YYYY-MM-DD
DATETIME - format: YYYY-MM-DD HH:MI:SS
SMALLDATETIME - format: YYYY-MM-DD HH:MI:SS
TIMESTAMP - format: a unique number
Note: The date types are chosen for a column when you create a new table in your database!

We use the following SELECT statement:

```sql
SELECT * FROM Orders WHERE OrderDate='2008-11-11'
```

Note: Two dates can easily be compared if there is no time component involved!

If we use the same SELECT statement as above:

```sql
SELECT * FROM Orders WHERE OrderDate='2008-11-11'
```

we will get no result! This is because the query is looking only for dates with no time portion.

Tip: To keep your queries simple and easy to maintain, do not use time-components in your dates, unless you have to!

SQL CREATE VIEW Statement
In SQL, a view is a virtual table based on the result-set of an SQL statement.

A view contains rows and columns, just like a real table. The fields in a view are fields from one or more real tables in the database.

You can add SQL statements and functions to a view and present the data as if the data were coming from one single table.

A view is created with the CREATE VIEW statement.

CREATE VIEW Syntax

```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

Note: A view always shows up-to-date data! The database engine recreates the view, every time a user queries it.

SQL CREATE VIEW Examples
The following SQL creates a view that shows all customers from Brazil:

Example

```sql
CREATE VIEW [Brazil Customers] AS
SELECT CustomerName, ContactName
FROM Customers
WHERE Country = 'Brazil';
```

We can query the view above as follows:

Example

```sql
SELECT * FROM [Brazil Customers];
```

The following SQL creates a view that selects every product in the "Products" table with a price higher than the average price:

Example

```sql
CREATE VIEW [Products Above Average Price] AS
SELECT ProductName, Price
FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products);
```

We can query the view above as follows:

Example

```sql
SELECT * FROM [Products Above Average Price];
```

SQL Updating a View
A view can be updated with the CREATE OR REPLACE VIEW statement.

SQL CREATE OR REPLACE VIEW Syntax

```sql
CREATE OR REPLACE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

The following SQL adds the "City" column to the "Brazil Customers" view:

Example

```sql
CREATE OR REPLACE VIEW [Brazil Customers] AS
SELECT CustomerName, ContactName, City
FROM Customers
WHERE Country = 'Brazil';
```

SQL Dropping a View
A view is deleted with the DROP VIEW statement.

SQL DROP VIEW Syntax

```sql
DROP VIEW view_name;
```

The following SQL drops the "Brazil Customers" view:

Example

```sql
DROP VIEW [Brazil Customers];
```

Source : https://www.w3schools.com/sql/sql_quickref.asp

```sql
SELECT COUNT(DISTINCT name) from table;
```

```sql
SELECT COUNT(DISTINCT (name)) from table;
```

```sql
SELECT DATE(payment_date) FROM payment;
```

DATE function removes timestamp information, just keeps the date

UN EJEMPLO, usando GROUP BY de dos columnas:

```sql
SELECT staff_id, customer_id , SUM(amount)
FROM payment
GROUP BY staff_id, customer_id
ORDER BY SUM (amount);
```

Hacer esto es lo mismo que un DISTINCT, no nos muestra datos repetidos:

```sql
SELECT numbers
FROM list_of_numbers
GROUP BY numbers;
```

```sql
SELECT COUNT(numbers)
FROM list_of_numbers
GROUP BY COUNT(numbers);
```
