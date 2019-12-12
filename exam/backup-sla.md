#Backup Service Level Agreement<br /> 
<!-- I am doing this for fun, you know --><br /> 
![#f03c15](https://placehold.it/15/f03c15/000000?text=+) **Coverage**: Will be stored all database server data and data from master server. Also data from node, mysqld and bind exporter will be collected. 
The bind slave is skipped because slave is always synchronizing with master.  

![#f03c15](https://placehold.it/15/ffa500/000000?text=+) **RPO**: acceptable data loss is around 24 hours.

![#f03c15](https://placehold.it/15/c5f015/000000?text=+) **Versioning**: Will be stored a few different versions (minimum: 3) in case of any unstable/non-working backups. 
The all progress will be easily tracked and can be returned with backup. 

![#f03c15](https://placehold.it/15/00ff00/000000?text=+) **Retention**: All backups will be stored around a month. All backups which older than month will be deleted automatically. 

![#f03c15](https://placehold.it/15/0079bf/000000?text=+) **Usability**: It can be verified with checking time of creation and readablity/writablity of data. **NB!** All backups make cron.d. 
Also backup must be restorable. It can be check by some simple tests. You just need to copy it back to machine with problems then put it to the right place and try how it will work.

![#f03c15](https://placehold.it/15/0c3953/000000?text=+) **Restoration criteria**: If something does not work as should, you have to restore fully working backup. Also in case of the any disaster backup should be restored.
Mysql backup has been done with mysqldump, so the procedure of returning is quite easy. All others backus have been made with cron.d. All cron activity is written in /etc/cron.d/update
In that file you can check the local and the remote path of backups.

![#f03c15](https://placehold.it/15/7f00ff/000000?text=+) **RTO**: It takes around 90 minutes to restore all backups back.
