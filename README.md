# dropbox-backup
Userspace backup utility that maintains backup directories from ~/Dropbox.

### Global installation
```
$ git clone https://github.com/nielsvm/dropbox-backup.git /opt/dropbox-backup
```

### For every user account

##### One-time initialization
```
$ /opt/dropbox-backup/db sync
INITIALIZING - press CTRL+C when done!

This computer isn't linked to any Dropbox account...
Please visit https://www.dropbox.com/cli_link_nonce?nonce= to link this device.

This computer is now linked to Dropbox. Welcome ...
^C
Starting...
Downloading file list...
Syncing (5 files remaining)
...
Downloading 5 files...
Sync done
```

##### Backup

###### Manually
```
$ /opt/dropbox-backup/db backup $HOME/daily
...
sent 15068383 bytes  received 114 bytes  10045664.67 bytes/sec
total size is 15195904  speedup is 1.01
```

###### Cron
```
@hourly /opt/dropbox-backup/db backup /home/USER/hourly
5 4 * * * /opt/dropbox-backup/db backup /home/USER/daily
5 4 * * 6 /opt/dropbox-backup/db backup /home/USER/weekly
```
