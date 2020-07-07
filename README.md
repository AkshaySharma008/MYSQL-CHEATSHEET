# MYSQL-CHEATSHEET

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
      a. select tables;
      
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














