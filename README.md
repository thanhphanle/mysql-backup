# mysql-backup
A simple way to backup MySQL database in bash script, this script is a copy from author Rahul Kumar.

## How to setup in CentOS

**Step 1.** Clone or copy sh script into your machine at directory `/opt/scripts`

**Step 2.** Open script file and update config in section below:
```properties
DB_BACKUP_PATH='/home/backup/mysql'
MYSQL_HOST='localhost'
MYSQL_PORT='3306'
MYSQL_USER='user'
MYSQL_PASSWORD='password'
DATABASE_NAME='exampledb'
BACKUP_RETAIN_DAYS=30
```

**Step 3.** Grant execution permission for script file
```sh
$ chmod +x /opt/scripts/mysql-backup.sh
```

**Step 4.** Create a cron job to run script daily

To open and configure crontab:
```
$ crontab -e
```

Add new cron job (run at 2am everyday) and save it:
```
0 2 * * * /opt/scripts/mysql-backup.sh
```

Restart cron service to apply new job:
```
$ systemctl restart crond
```

## Reference

* [A Simple Bash Script for MySQL Database Backup](https://tecadmin.net/bash-script-mysql-database-backup/)
