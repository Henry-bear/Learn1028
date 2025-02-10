# Task 1
```
SELECT * FROM users WHERE created_at > '2025-01-01';
```

# Task 2
**建立 website 資料庫**  
```
CREATE DATABASE website;
```
**建立 member Table**  
```
CREATE TABLE member (
    -> id BIGINT AUTO_INCREMENT PRIMARY KEY,
    -> name VARCHAR(255) NOT NULL,
    -> username VARCHAR(255) NOT NULL,
    -> password VARCHAR(255) NOT NULL,
    -> follower_count INT UNSIGNED NOT NULL DEFAULT 0,
    -> time DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP
    -> );
```
