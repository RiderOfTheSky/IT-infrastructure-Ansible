#backup restore plan
#useful links: https://docs.ansible.com/ansible/latest/modules/cron_module.html
#useful advice: make backup throw "copy"

Backup restore plan:
**All restore things should be done with user BACKUP or ROOT** 
1) MySQL database backup: enter the command below to restore database from backup.<br />
 Command: mysql -u [user] -p [database_name] < [filename].sql

The location of the local backup is next: /backup/mysql/*[filename]*.sql<br />
The location of the remote backup is next: /srv/backup/all<br />
The [database name] is the file where to restore the backup of database. <br />


2) The DNS database
The location of the **local** backup is next: /backup/dns/ - There are 3 different files, one of them is database, others are config files<br />
The location of the **remote** backup is next: /srv/backup/all<br />
To restore it, just put all _(if necessary)_ files into BIND installation directory. By default it is /etc/bind/<br />
if backup is needed from **local** machine, use this command: cp /backup/dns/*file name* /etc/bind/<br />
if backup is needed from **remote** machine, use this command: scp backup@*ip of the remote machine*/backup/dns/*file name* *location of BIND directory*<br />
