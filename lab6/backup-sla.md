#Backup Service Level Agreement

Coverage: Will be stored all database server data and data from master server. The web server and slave is skipped because slave is always synchronizing with master and same with the web server. 

RPO: acceptable data loss is around 36 hours.

Versioning: Will be stored a few different versions in case of any unstable/non-working backups. The all progress will be easily tracked and can be returned with backup. 

Retention: All backups will be stored around a month. All backups which older than month will be deleted automatically.

Usability: It can be verified with checking time of creation and readable/writable of data. Also backup must have be restorable. It can be done by some simple tests.

Restoration criteria: If something does not work as should, you have to restore fully working backup. Also in case of the any disaster backup should be restored.

RTO: It takes around 20 minutes to restore all backups back.
