Simple script to backup and restore disks efficiently using partclone
=====================================================================

You want most simple clonezilla like implementation ?

```
disk-backup-restore-script-generator.sh /dev/sdX /mnt/backup-dir gzip gunzip
```

To backup - prefix lines by # if you want to omit a partition
```
  sh /mnt/backup-dir/backup.sh
```
If a partition is complete a .ok file will be touched.
You can resume, succeeded partitions will be skipped.

To restore:
```
  ./restore.sh /mnt/backup-dir /dev/sda ""
  ./restore.sh /mnt/backup-dir /dev/nvme0n1 "p"
```

Dependencies: lsblk, partclone

I'd appreciate linux distribution packaging this *OR* tell me there is a better
or more simple alternative so that I can archive this :-)

What this script will never
---------------------------
have progress bars for overall progress
be complicated
prevent you from data loss - know or learn what you're doing.
