#数据库基础
+ SQL语法
    + SQL对大小写不敏感
    + DML（数据操作语言
        + SELECT
        + UPDATE
        + DELETE
        + INSERT INTO
    + DDL（数据定义语言
        + CREATE DATABASE
        + ALTER DATABASE
        + CREATE TABLE
        + ALTER TABLE
        + DROP TABLE
        + CREATE INDEX
        + DROP INDEX
##词汇
+ RAID
+ NoSQL
+ Phantom reads
+ dirty reads
+ transaction
    + atomic
    + durable
+ Constraints
    + NOT NULL
    + UNIQUE 每个表可有多个unique约束，但只能有一个primary key 
    + PRIMARY KEY 自动是unique的
    + FOREIGN KEY
    + CHECK 限制列中值的范围
    + DEFAULT
## 基本语法
+ insert
+ update
+ delete
+ order by
+ where
+ select
+ distinct
+ 
+ PRIMARY KEY
    什么是主键
    + CREATE TABLE Persons 
        + PRIMARY KEY (ID)
        + ID int NOT NULL PRIMARY KEY
    + ALTER TABLE Persons
        + DROP PRIMARY KEY
        + ADD PRIMARY KEY (ID)
        + ADD CONSTRAINT PK_person PRIMARY KEY (ID, LastName)
+ FOREIGN KEY