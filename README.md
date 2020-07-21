## What is SQL?
   SQL stands for Structured Query Language,which is a conputer language for storing,manipulating 
   and retrieving data stored in relational databases.

## MYSQL-CHEATSHEET

#### 1. Login to MySQL 
      a. mysql -u root -p
      
#### 2. Quit
      a. exit;
      
#### 3. Display all DB
      a. show databases;
      
#### 4. Create a database
      a. create database mytest;
      
#### 5. To use mytest database
      a. use mytest;
      
#### 6. Delete a database
      a. DROP DATABASE mytest;
      
#### 7. To get the version of mysql
      a. select version();
 
#### 8. To get the present date
      a. select now();
      
#### 9. To get the version of mysql
      a. select version();
      
#### 10. To use the particular database
      a. use mytest;
      
#### 11. To know in which database you are working with
      a. select database();
      
#### 12. To display number of tables
      a. show tables;
      
#### 13. To display particular table
      a. desc table_name;
      
#### 14. To create a table inside a database
      a. create table student(id int , name char(10)); 

#### 15. To get table primary key/foreign key etc info.
      a. show create table student \G; 

#### 16. To add the data into table.
      a. insert into student values (1,'Akshay');
      b. insert into student (id,name) values (2,'John'),(3,'Wick');

#### 17. To display all data in table 
      a. select * from student;
      
#### 18. select particular data from table 
      a. select  col_name   from  table_name   where  condition;
      eg. select id,name form student where id=2;
      
#### 19. To add any column after sometime / alter table
      a. alter table table_name add column column_name type null_condition
      eg. alter table student add column address varchar(30) not null;

#### 20. To delete any column of the table
      a. alter table table_name drop column column_name;
      eg. alter table student drop column address;

#### 21. To add primary key contrain to  any column of the table
      a. alter table table_name add primary key (col_name);
      eg. alter table student add primary key (id);
      
#### 22. To add Primary Key constrain
      a. ALTER TABLE table_name ADD PRIMARY KEY(ID);

#### 23. To drop Primary Key constrain
      a. ALTER TABLE table_name DROP PRIMARY KEY;
      
#### 24. To add Foreign Key while creating New table 
      a.create Table Orders 
        (OrderID int NOT NULL,
         OrderNumber int NOT NULL,
         PersonID int,
         PRIMARY KEY (OrderID),
         FOREIGN KEY (PersonId) references Person(ID) 
         );
      b. Person Table has been created already   

#### 25. To drop FORIEGN Key constrain
      a. alter table Orders drop FOREIGN KEY Orders_ibfk_1;
      
#### 26. To Add FOREIGN KEY constrain
      a. alter table Orders add FOREIGN KEY (PersonId) REFERENCES Person(ID);
      
#### 27. To start Transaction between tables 
      a.  start transaction;
      
#### 28. To Delete a record from table 
      a. delete from Person where id=1;

#### 29. To UNDO deletion using rollback 
      a. rollback;
   
#### 30. Delete a table
      a. DROP table table_name;
      
#### 31. INTEGRITY-CONSTRAINTS 
      a. NULL Constraint - NOT NULL (add this while creating table and mention after Col_name)
            eg. ID int(6) NOT NULL
      b. UNIQUE Constraint -
            eg. ID int(6) UNIQUE
            ** NOT NULL UNIQUE will behave as PRIMARY KEY
      c. PRIMARY Constraint - 
            eq.PRIMARY KEY(ID);
      d. FOREIGN KEY Constraint - 
            - The FOREIGN KEY for a table must be a PRIMARY KEY for the other table
            - The table which has PRIMARY KEY called as PARENT TABLE
            - The table which has used that PRIMARY KEY called as CHILD TABLE.
            - This key establishes the MULTIPLE RELATION between them (MUL)
            eg. FOREIGN KEY(C_ID) REFERENCES CUSTOMER(CID));
           ** If you want to remove the primary key , need to remove the reference key before 
              from child table.
      e. CHECK constraint
            eg. AGE int NOT NULL CHECK (AGE>18)
            - ERROR 3819 (HY000): Check constraint 'Student_chk_1' is violated.
      f. DEFAULT constraint
            eg. AGE int DEFAULT 18;
      g. AUTO INCREMENT
            eg. S_NO int NOT NULL AUTO_INCREMENT
            
#### 32. Comparison Operators
      a. '=' (equal to),
      b. '<>' or '!=' (not equal to),
      c. '>' (greater than),
      d. '<' (less than),
      e. '>=' (greater than or equal to),
      f. '<=' (less than or equal to),
      eg. SELECT name, quantity FROM products WHERE quantity <= 2000;
      
#### 33. String Matching 
      a. we can perform pattern matching using operator LIKE (or NOT LIKE) with wildcard characters.
         - The wildcard '_' matches any single character
         - '%' matches any number of characters (including zero)
         as,
         a. 'abc%' matches strings beginning with 'abc';
         b. '%xyz' matches strings ending with 'xyz';
         c. '%aaa%' matches strings containing 'aaa';
         d. '___' matches strings containing exactly three characters; and
         e. 'a_b%' matches strings beginning with 'a', followed by any single character,
            followed by 'b', followed by zero or more characters.
     eg. SELECT name, price FROM products WHERE name LIKE 'PENCIL%’;
     
#### 34. Arithmetic and Logical Operators
       a.   
            - addition
            - substraction
            - multiplication
            - division
            - Modulus(Remainder)
      b.    
            - AND
            - OR
            - NOT
            - XOR
      eg. SELECT * FROM products WHERE quantity >= 5000 AND price < 1.24 AND name LIKE 'Pen %’;
          SELECT * FROM products WHERE NOT (quantity >= 5000 AND name LIKE 'Pen %');
          
#### 35. ORDER BY Clause
      a. Arrange the table in ascending / descending order
      eg. SELECT * FROM products WHERE name LIKE 'Pen %' ORDER BY price DESC;
          SELECT * FROM products WHERE name LIKE 'Pen %' ORDER BY price DESC, quantity;
          
#### 36. LIMIT Clause
      -  To display only first two rows
      eg. SELECT * FROM products ORDER BY price LIMIT 2;
      
#### 37. AS-alias
      - Define these names as to be the display names
      eq. SELECT productID AS ID, productCode AS Code,name AS Description, price AS `Unit Price`
         FROM products ORDER BY ID; 
         ** Use alias ID as reference
            
#### 38. CONCAT()
      - Concatinate two colums into single one and display
      eg. SELECT CONCAT(productCode, ' - ', name) AS `Product Description`, price FROM products;
      
#### 39. DISTINCT
      - A column may have duplicate values, we could use keyword DISTINCT to select only distinct values.
        We can also apply DISTINCT to several columns to select distinct combinations of these columns.
      eg. SELECT DISTINCT price AS `Distinct Price` FROM products;
      
#### 40. GROUP BY
      - The GROUP BY clause allows you to collapse multiple records with a common value into groups
      eg. SELECT * FROM products GROUP BY productCode;
            ** Only first record in each group is shown
           
#### 41. GROUP BY AGGREGATE
      - we can apply GROUP BY Aggregate functions to each group to produce group summary report.
      as, 
         - COUNT
         - MIN
         - MAX
         - AVG
         - SUM
         - STD
         - GROUP_CONCAT
      eg. SELECT COUNT(*) AS `Count` FROM products;
            ** Function COUNT(*) returns the number of rows selected
          SELECT MAX(price), MIN(price), AVG(price), STD(price), SUM(quantity) FROM products;  
          
#### 42. UPDATE RECORDS/DATA 
      - To modify existing data, use UPDATE ... SET command, with the following syntax:
      eg. UPDATE products SET price = price * 1.1;
            ** Increase the price by 10% for all products
          UPDATE products SET quantity = quantity - 100 WHERE name = 'Pen Red';
            ** Modify selected rows
         
#### 43. DELETING ROWS
      - DELETE FROM tableName    ** to drop table
      - DELETE FROM tableName WHERE criteria 
            ** to drop items which satify the criteria
         
          
           
  
            
          

   












