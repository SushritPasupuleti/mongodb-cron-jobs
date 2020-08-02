# Backing Up MongoDB with Cron

> Create the `mongobackup.sh` shell script

> make `mongobackup.sh` into an executable

```shell
chmod +x mongobackup.sh
```

```
crontab -e
```

Enter the following content into the editor (Skip the initial comments if already present)
```cron
# ┌───────────── minute (0 - 59)
# │ ┌───────────── hour (0 - 23)
# │ │ ┌───────────── day of month (1 - 31)
# │ │ │ ┌───────────── month (1 - 12)
# │ │ │ │ ┌───────────── day of week (0 - 6) (Sunday to Saturday;
# │ │ │ │ │                                       7 is also Sunday on some systems)
# │ │ │ │ │
# │ │ │ │ │
# * * * * *  command_to_execute

00 00 * * * /path/to/script/mongobackup.sh
#backup starts at midnight everyday
```

### Tips

- [Use `crontab.guru` ](https://crontab.guru/) to check if a schedule behaves as expected

- Recommended solution, if mongo instance is inside a container, and the backup directory is in a mapped volume (set intervals to be more tighter).