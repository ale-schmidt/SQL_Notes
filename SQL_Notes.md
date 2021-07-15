# SQL Statements

This document provides a list of SQL statements used in the course _Learning SQL Programming_ from LinkedIn Learning.

Note that this list contains statements which are improper (they have syntax errors) and statements which are incorrect (they do not achieve the desired goal).

https://www.w3schools.com/sql
https://www.linkedin.com/learning/learning-sql-programming-8382385/learning-sql-programming?u=2154233
https://www.linkedin.com/learning/learning-sql-programming-8382385/learning-sql-programming

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

There are two wildcards often used in conjunction with the LIKE operator:

<!-- The percent sign (%) represents zero, one, or multiple characters
The underscore sign (_) represents one, single character
Note: MS Access uses an asterisk (*) instead of the percent sign (%), and a question mark (?) instead of the underscore (_). -->

The percent sign and the underscore can also be used in combinations!
You can also combine any number of conditions using AND or OR operators.

```sql
LIKE  Operator	                Description
WHERE CustomerName LIKE 'a%'	Finds any values that start with "a"
WHERE CustomerName LIKE '%a'	Finds any values that end with "a"
WHERE CustomerName LIKE '%or%'	Finds any values that have "or" in any position
WHERE CustomerName LIKE '_r%'	Finds any values that have "r" in the second position
WHERE CustomerName LIKE 'a_%'	Finds any values that start with "a" and are at least 2 characters in length
WHERE CustomerName LIKE 'a__%'	Finds any values that start with "a" and are at least 3 characters in length
WHERE ContactName LIKE 'a%o'	Finds any values that start with "a" and ends with "o"
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

SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2, A.City
FROM Customers A, Customers B
WHERE A.CustomerID <> B.CustomerID
AND A.City = B.City
ORDER BY A.City;
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

<!-- Here are some examples showing different LIKE operators with '%' and '_' wildcards: -->

```sql
LIKE    Operator	                                                Description
WHERE   CustomerName LIKE 'a%'	                                        Finds any values that starts with "a"
WHERE   CustomerName LIKE '%a'	                                        Finds any values that ends with "a"
WHERE   CustomerName LIKE '%or%'	                                    Finds any values that have "or" in any position
WHERE   CustomerName LIKE '_r%'	                                        Finds any values that have "r" in the second position
WHERE   CustomerName LIKE 'a__%'	                                    Finds any values that starts with "a" and are at least 3 characters in length
WHERE   ContactName  LIKE 'a%o'	                                        Finds any values that starts with "a" and ends with "o"
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
