<div class="alert alert-warning" role="alert">
It is only user's home directories under <code>/home/</code> are backed up - <em>no other directories on the cluster file system are backed up!</em>
</div>

# File Backups (/home/ only)

All users' `/home/` directories are backed up regularly.  _Note that no other directories than `/home/` are backed up_.  The below two types of backups are performed.

## DIY-recovery backups
* **Weekly** backups to another disk (starting Fridays @ 11:00 PM)
* Backup history: **Only last backup**
* Recovery: Do it yourself by copying from `/backup/home/$USER/`
  - Modified files: Previous version of a modified file can be recovered from the backup until next backup runs
  - Deleted files: A deleted file can be recovered from the backup until next backup runs
* Technical details: `rsync -avzH --delete /home/$USER/` is used to backup

## Archival backups
* **Nightly** backups to tape (full every weekend and incremental nightly)
* Backup history: **~12 months**
* Recovery: Contact [sysadm]
  - Modified files: Previous versions of a modified file can be recovered from the archive for up to 12 months
  - Deleted files: A deleted file can be recovered from the archive for up to 12 months

NOTE: Archival backups were temporarily disabled from 2017-04-25 to 2017-05-19  for purposes of troubleshooting why the master (the head node) kept crashing.  No backups are available during that period.


[sysadm]: {{ '/about/about.html' | relative_url }}
