# Developer Reference – General Commands & Best Practices

This document serves as a **quick reference guide** for commonly used **PHP, Laravel, server, database, and Unix commands**. It aims to improve consistency, speed, and reliability during development, debugging, and deployment workflows.

---

## Server & Services

### Restart Apache Server

Restart the Apache web server after configuration or PHP version changes.

```bash
sudo /etc/init.d/apache2 restart
```

---

## Support & Ticketing Portals

### Network Team Tickets

[https://help.uvdesk.com/en/customer/tickets](https://help.uvdesk.com/en/customer/tickets)

### Customer Tickets

[https://webkul.uvdesk.com/en/member/login](https://webkul.uvdesk.com/en/member/login)

---

## Symlinks (Soft Links)

Create a symbolic link so changes reflect in both locations.

```bash
ln -s /complete/path/to/source /complete/path/to/destination
```

**Example:**

```bash
ln -s /home/users/devansh.akeneo/www/html/git-prestashop-akeneo6/akeneo-prestashop-connector/src/Webkul Webkul
```

---

## Download & Extract

### Download from URL

```bash
wget <url>
```

### Extract `.tar.gz` Files

```bash
tar -xvzf file.tar.gz
```

---

## PHP Version Switching (Apache)

> Always restart Apache after switching PHP versions.

### Switch PHP 8.2 → 8.1

```bash
sudo a2dismod php8.2
sudo a2enmod php8.1
sudo /etc/init.d/apache2 restart
sudo update-alternatives --set php /usr/bin/php8.1
```

### Switch PHP 8.1 → 8.2

```bash
sudo a2dismod php8.1
sudo a2enmod php8.2
sudo /etc/init.d/apache2 restart
sudo update-alternatives --set php /usr/bin/php8.2
```

### Switch PHP 7.4 → 8.1

```bash
sudo a2dismod php7.4
sudo a2enmod php8.1
sudo /etc/init.d/apache2 restart
sudo update-alternatives --set php /usr/bin/php8.1
```

### Switch PHP 8.0 → 7.4

```bash
sudo a2dismod php8.0
sudo a2enmod php7.4
sudo /etc/init.d/apache2 restart
sudo update-alternatives --set php /usr/bin/php7.4
```

### Switch PHP 8.1 → 7.4

```bash
sudo a2dismod php8.1
sudo a2enmod php7.4
sudo /etc/init.d/apache2 restart
sudo update-alternatives --set php /usr/bin/php7.4
```

### Switch PHP 8.1 → 8.0

```bash
sudo a2dismod php8.1
sudo a2enmod php8.0
sudo /etc/init.d/apache2 restart
sudo update-alternatives --set php /usr/bin/php8.0
```

### Switch PHP 7.4 → 8.0

```bash
sudo a2dismod php7.4
sudo a2enmod php8.0
sudo /etc/init.d/apache2 restart
sudo update-alternatives --set php /usr/bin/php8.0
```

### Switch PHP 8.2 → 8.0

```bash
sudo a2dismod php8.2
sudo a2enmod php8.0
sudo /etc/init.d/apache2 restart
sudo update-alternatives --set php /usr/bin/php8.0
```

---

## Switch to Root User

```bash
sudo -su root
```

---

## MySQL / MariaDB Commands

### Connect to MySQL

```bash
mysql -u USERNAME -pPASSWORD -h HOSTNAME DATABASE
```

**Example:**

```bash
mysql -u akeneo_pim -p akeneo_pim
```

---

### Export Database (Dump)

```bash
mysqldump -u user -p databasename > databaseBackup.sql
```

**Example:**

```bash
mysqldump -u root -p bitnami_akeneo_7 > databaseBackup.sql
```

### Dump a Single Table

```bash
mysqldump -u root -p databasename tableName > tableBackup.sql
```

---

### Import Database

```bash
mysql -u user -p databasename < databaseBackup.sql
```

---

### Get Database Size

```sql
SELECT table_schema AS "Database Name",
       ROUND(SUM(data_length + index_length) / 1024 / 1024, 2) AS "Database Size (MB)"
FROM information_schema.TABLES
GROUP BY table_schema;
```

---

## System Monitoring

```bash
htop
free -h
```

---

## Network Utilities

### Get IP / Check Connectivity

```bash
ping <url>
```

---

## PHP Debugging

### Show Function Call Stack

```php
debug_backtrace();
```

---

## Filesystem Utilities

### Find Empty Directories

```bash
find . -type d -empty
```

### Count Files Recursively

```bash
find <DIR_NAME> -type f | wc -l
```

### Check Storage Usage in GB

```bash
du -h . 2>/dev/null | grep '[0-9\\.]\\+G'
```

---

## File Transfer (rsync)

### Remote → Local

```bash
rsync -avz -e "ssh -i <key-file>" user@ip:/path/to/source /destination --progress
```

### Local → Remote

```bash
rsync -avz -e "ssh -i <key-file>" /local/path user@ip:/path/to/destination --progress
```

---

## Laravel Artisan Commands

### List All Commands

```bash
php artisan list
```

### Compile Blade Views

```bash
php artisan view:cache
```

### Measure Performance & Resource Usage

```bash
/usr/bin/time -v php artisan q:w --sleep=3 --timeout=0 --queue=default
```

---

## Git & Pull Request Utilities

### Fetch Pull Request (master branch)

```bash
git fetch origin pull/30/head:devansh-pal-webkul
```

### Fetch Pull Request (custom branch)

```bash
git fetch origin pull/<PR_NUMBER>/head:<BRANCH_NAME>
```

### Verify Last Commit

```bash
git log
```

---

### View PR Diff

```text
https://github.com/<org>/<repo>/pull/<PR>.diff
https://patch-diff.githubusercontent.com/raw/<org>/<repo>/pull/<PR>.diff
```

### Git Cheat Sheet

[https://git-scm.com/cheat-sheet](https://git-scm.com/cheat-sheet)

---

**Tip:** Keep commands minimal, tested, and well-documented to help others use them safely and effectively.
