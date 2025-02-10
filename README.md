# Task 1
**Install MySQL server**

<img width="350" alt="MySQL" src="https://github.com/user-attachments/assets/bc159e7d-41fd-4366-9da6-4f37a64b9844" />

# Task 2
**Create database and table in your MySQL server**

**建立 website 資料庫**  
```sql
CREATE DATABASE website;
```
<img width="643" alt="creat-database" src="https://github.com/user-attachments/assets/a957efe5-ff0f-48e7-ae08-b2168e6f501e" />

**建立 member 資料表**  
```sql
CREATE TABLE member (
    -> id BIGINT AUTO_INCREMENT PRIMARY KEY,
    -> name VARCHAR(255) NOT NULL,
    -> username VARCHAR(255) NOT NULL,
    -> password VARCHAR(255) NOT NULL,
    -> follower_count INT UNSIGNED NOT NULL DEFAULT 0,
    -> time DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP
    -> );
```
<img width="502" alt="creat-table-member" src="https://github.com/user-attachments/assets/9d29ba54-cfb3-4e97-9676-edd57e821a6c" />

## 資料表資訊 
<img width="714" alt="describe-member" src="https://github.com/user-attachments/assets/2a7db469-90a0-4f7f-946f-fd7e03b072b1" />

# Task 3
**SQL CRUD （建立、刪除、查詢、更新）**

* INSERT a new row to the member table where name, username and password must
be set to test. INSERT additional 4 rows with arbitrary data.
```sql
INSERT INTO member (name, username, password)
    -> VALUES ('test', 'test', 'test');
INSERT INTO member (name, username, password, follower_count)
    -> VALUES
    -> ('Henry', 'henry1107', '123456', 999),
    -> ('Cundi', 'cundi520', '654321', 888),
    -> ('Tom', 'tom8787', '87654321', 666),
    -> ('Alex', 'alex3838', 'password', 100);
```
<img width="550" alt="tesk3 1-1" src="https://github.com/user-attachments/assets/06e13ccf-d9a5-43b8-9dac-911921e0ce3c" />
<img width="707" alt="task3 1" src="https://github.com/user-attachments/assets/018a0514-4553-44b6-847f-a162de4f5bf6" />


* SELECT all rows from the member table.
```sql
SELECT * FROM member;
```
<img width="715" alt="member" src="https://github.com/user-attachments/assets/57888cf9-4707-48ea-ba68-87bf68034aca" />

* SELECT all rows from the member table, in descending order of time.
```sql
SELECT * FROM member ORDER BY time DESC;
```
<img width="715" alt="timeDESC" src="https://github.com/user-attachments/assets/eeca2996-71b8-4d3c-bd40-d5f5c9b2f1d6" />

* SELECT total 3 rows, second to fourth, from the member table, in descending order
of time. Note: it does not mean SELECT rows where id are 2, 3, or 4.
```sql
SELECT * FROM member ORDER BY time LIMIT 3 OFFSET 1;
```
<img width="711" alt="Limit" src="https://github.com/user-attachments/assets/869909ba-1db1-4a03-a001-0ed557db42f6" />

* SELECT rows where username equals to test.
```sql
SELECT * FROM member WHERE username = 'test';
```
<img width="721" alt="user-test" src="https://github.com/user-attachments/assets/9e1bfb43-ab38-4db7-b14f-c01c0a4200a0" />

* SELECT rows where name includes the es keyword.
```sql
SELECT * FROM member WHERE name LIKE '%es%';
```
<img width="719" alt="name-es" src="https://github.com/user-attachments/assets/de2f3f4c-3ccb-41df-b857-f967b70f5b7a" />

* SELECT rows where both username and password equal to test.
```sql
SELECT * FROM member WHERE username = 'test' AND password = 'test';
```
<img width="714" alt="usernameANDpassword" src="https://github.com/user-attachments/assets/0fcc874f-78cf-4327-a290-0583e06255da" />

* UPDATE data in name column to test2 where username equals to test.
```sql
UPDATE member SET name = 'test2' WHERE username = 'test';
```
<img width="716" alt="updatename" src="https://github.com/user-attachments/assets/aa09532d-d2d2-4c24-a65f-42f6da4a7aea" />

# Task 4
**SQL Aggregation Functions (聚合函數)**
* SELECT how many rows from the member table.
```sql
SELECT COUNT(*) AS total_rows FROM member;
```
<img width="694" alt="countRows" src="https://github.com/user-attachments/assets/1d649964-a461-4d60-93f7-cd13b70d1e73" />

* SELECT the sum of follower＿count of all the rows from the member table.
```sql
SELECT SUM(follower_count) AS total_followers FROM member;
```
<img width="715" alt="sumfollower" src="https://github.com/user-attachments/assets/161e2898-940a-4e55-bb1f-16506e7ab2a5" />

* SELECT the average of follower＿count of all the rows from the member table.
```sql
SELECT AVG(followers_count) AS average_followers FROM member;
```
<img width="716" alt="avgfollowers" src="https://github.com/user-attachments/assets/7c4ee710-b14f-4791-a8f7-d5ea4ac0dea0" />

* SELECT the average of follower＿count of the first 2 rows, in descending order of follower_count, from the member table.
```sql
SELECT AVG(followers_count) AS average_top2_followers
FROM (
SELECT follower_count
FROM member
ORDER BY follower_count DESC
LIMIT 2
) AS top2;
```
<img width="608" alt="avgfollowerslimit" src="https://github.com/user-attachments/assets/560efd5b-8f13-4670-b010-6d7502a0d6ed" />
