## Create a New MySQL User
Open your terminal and log into MySQL as root:
```bash
mysql -u root -p
```
Then run these commands:

#### Create the user
```SQL
CREATE USER 'nextuser'@'localhost' IDENTIFIED BY 'StrongPassword123!';
```
 
#### Create database & Grant permissions
```SQL
GRANT ALL PRIVILEGES ON your_database_name.* TO 'nextuser'@'localhost';
FLUSH PRIVILEGES;
```

#### Test the user
```SQL
mysql -u nextuser -p
```
Then enter your password
