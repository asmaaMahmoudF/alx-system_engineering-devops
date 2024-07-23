0x14-mysql

Project Overview

This project is focused on the installation, configuration, and management of MySQL databases. It covers various aspects of MySQL, including setting up a MySQL server, creating databases and users, performing basic SQL operations, and ensuring security and backups.

Learning Objectives

Understand the fundamentals of MySQL databases
Install and configure MySQL on a server
Create and manage databases and users
Perform basic SQL operations
Implement security measures for MySQL
Perform backups and restore operations
Requirements

A Linux-based operating system (Ubuntu recommended)
Basic understanding of SQL
Access to a terminal or command line interface
Setup Instructions

Installing MySQL
Update your package index:

bash
Copy code
sudo apt update
Install MySQL server:

bash
Copy code
sudo apt install mysql-server
Secure the MySQL installation:

bash
Copy code
sudo mysql_secure_installation
Configuring MySQL
Log in to the MySQL root user:

bash
Copy code
sudo mysql -u root -p
Create a new database:

sql
Copy code
CREATE DATABASE my_database;
Create a new user and grant permissions:

sql
Copy code
CREATE USER 'my_user'@'localhost' IDENTIFIED BY 'my_password';
GRANT ALL PRIVILEGES ON my_database.* TO 'my_user'@'localhost';
FLUSH PRIVILEGES;
Basic SQL Operations

Creating a Table
sql
Copy code
USE my_database;

CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
Inserting Data
sql
Copy code
INSERT INTO users (name, email) VALUES ('John Doe', 'john.doe@example.com');
Querying Data
sql
Copy code
SELECT * FROM users;
Security Measures

Remove anonymous users:

sql
Copy code
DELETE FROM mysql.user WHERE User='';
Disallow root login remotely:

sql
Copy code
UPDATE mysql.user SET Host='localhost' WHERE User='root';
Remove the test database:

sql
Copy code
DROP DATABASE IF EXISTS test;
DELETE FROM mysql.db WHERE Db='test' OR Db='test\\_%';
Reload privilege tables:

sql
Copy code
FLUSH PRIVILEGES;
Backup and Restore

Backup
bash
Copy code
mysqldump -u root -p my_database > my_database_backup.sql
Restore
bash
Copy code
mysql -u root -p my_database < my_database_backup.sql
Conclusion

This project provides a solid foundation for working with MySQL databases. By following the steps and examples provided, you should be able to install, configure, and manage MySQL effectively. For further reading and advanced topics, refer to the official MySQL documentation.

Resources

MySQL Documentation
DigitalOcean MySQL Tutorials