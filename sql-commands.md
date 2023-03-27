* Useful SQL commands

* Show databases
SHOW DATABASES;

* Show users
SELECT user FROM mysql.user;

* Create user
CREATE USER 'username'@'host' IDENTIFIED WITH authentication_plugin BY 'password';

CREATE USER 'rave'@'localhost' IDENTIFIED WITH authentication_plugin BY '!Qasw23edfr4'; --> not working without the authentication_plugin loaded

CREATE USER 'rave'@'localhost' IDENTIFIED WITH mysql_native_password BY '!Qasw23edfr4';

* Show SQL tables information
SELECT table_name FROM INFORMATION_SCHEMA.TABLES WHERE table_type = 'BASE TABLE';

* Create a database
CREATE DATABASE modx_db DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;

CREATE DATABASE modx_db_last CHARACTER SET utf8mb3 COLLATE utf8mb3_general_ci;

* Grant privileges and create a user with a provided password
GRANT ALL PRIVILEGES ON modx_db.* TO 'modx_user'@'localhost' IDENTIFIED BY 'PASSWORD';

GRANT ALL PRIVILEGES ON modx_db_v303_utf8mb3.* TO 'rave'@'localhost' IDENTIFIED BY '!Qasw23edfr4';

* Show database information schema
SELECT table_name FROM INFORMATION_SCHEMA.TABLES WHERE table_type = 'BASE TABLE';