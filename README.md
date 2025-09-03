# ERPNext-Database-Connection-Issue-Resolve


```
SELECT User, Host FROM mysql.user;
```

**Get the DB Name and Password from your site from `ERPNext` Backend**

```
{
 "active_domains": "[\"All\"]",
 "allow_cors": "*",
 "db_name": "_597a44263fdffa50",
 "db_password": "XwKEOrR6FPGmipNM",
 "db_type": "mariadb",
 "developer_mode": 1,
 "encryption_key": "CTcVm3En8p4UiMkFjxCIy5U8KwdbZmQUZ8LdUkryU0w=",
 "server_script_enabled": true,
 "user_type_doctype_limit": {
  "employee_self_service": 30
 }

```

**Create a user with your ERPNext `DB Name` and `DB Password`**

# Way - 01


```
-- Add new user

CREATE USER '_597a44263fdffa50'@'%' IDENTIFIED BY '5l41wzIZ3udw1V2W';
```

# Way - 02

```
-- Update existing user to allow from any host
RENAME USER '_597a44263fdffa50'@'10.0.4.4' TO '_597a44263fdffa50'@'%';

```

# Need to apply for bot

```
-- Or alternatively create a new wildcard user (safer)
GRANT ALL PRIVILEGES ON `_597a44263fdffa50`.* TO '_597a44263fdffa50'@'%';
```

```

-- Don't forget to flush privileges
FLUSH PRIVILEGES;

```
