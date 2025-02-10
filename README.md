# Task 1
```
SELECT * FROM users WHERE created_at > '2025-01-01';
```

# Task 2
**建立 website 資料庫**  
```sql
CREATE DATABASE website;
```
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

# Task 3
**SQL 建立、刪除、查詢、更新**

*INSERT a new row to the member table where name, username and password must
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
*SELECT all rows from the member table.
```sql
SELECT * FROM member;
```
