## Create a New MySQL User
Open your terminal and log into MySQL as root:
```bash
mysql -u root -p
```

Then run these commands:

#### Create the user
Use `%` when you need to connect to the database remotely.

```sql
CREATE USER 'nextuser'@'%' IDENTIFIED BY 'StrongPassword123!';
```

**OR**

If you are using Docker:

```sql
CREATE USER 'nextuser'@'localhost' IDENTIFIED BY 'StrongPassword123!';
```

#### Create database & Grant permissions

```sql
CREATE DATABASE your_database_name;
SHOW DATABASES;
GRANT ALL PRIVILEGES ON your_database_name.* TO 'nextuser'@'%';
FLUSH PRIVILEGES;
```

> If you created the user with `'localhost'`, use:

```sql
GRANT ALL PRIVILEGES ON your_database_name.* TO 'nextuser'@'localhost';
FLUSH PRIVILEGES;
```

#### Test the user

```bash
mysql -u nextuser -p
```

Then enter your password.
