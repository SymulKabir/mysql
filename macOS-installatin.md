#### Install Homebrew (if you don’t already have it):

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

#### Update Homebrew:

```bash
brew update
```

#### Install MySQL:
```bash
brew install mysql
```

#### Start MySQL server:
```bash
brew services start mysql
```
Or manually:
```bash
mysql.server start
```

#### Secure MySQL installation:
```bash
mysql_secure_installation

```

#### Log in to MySQL:
```bash
mysql -u root -p
```



## How set/reset password in mysql

#### Kill any hanging processes
```bash
sudo pkill mysqld
```


#### Start MySQL in safe mode
In Terminal Tab A:

```bash
sudo /opt/homebrew/opt/mysql/bin/mysqld --skip-grant-tables --skip-networking --user=micple
```

#### Log in and reset the password
In Terminal Tab B:

```bash
mysql -u root
```
Once you are inside the MySQL prompt, run these commands:

```SQL
FLUSH PRIVILEGES;
ALTER USER 'root'@'localhost' IDENTIFIED BY 'YourNewPassword Here';
FLUSH PRIVILEGES;
exit;
```

#### Clean up
-- Go back to Tab A and press `Control + C` to stop the safe-mode server.
-- Start MySQL normally via Brew:

```bash
brew services start mysql
```


