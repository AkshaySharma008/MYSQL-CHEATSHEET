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
           ** If you want to remove the primary key , need to remove the reference key before from child table.
      e. CHECK constraint
            eg. AGE int NOT NULL CHECK (AGE>18)
            - ERROR 3819 (HY000): Check constraint 'Student_chk_1' is violated.
      f. DEFAULT constraint
            eg. AGE int DEFAULT 18;
           
            
          

   












