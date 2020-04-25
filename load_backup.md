# Load Backup
### Possibly you have forgotten the borg commands, but your past self has taken care to leave this ready for you

borg list user@--ip--:/backups/--folder--
borg extract --info user@--ip--:/backups/--folder--::2020-04-24_09:16:33

join in the folder and
cp .ssh/ ~/ -r
cp backup.xml ~/
### remember to add this to the crontab
30 10 * * *
borg create -v -C zlib,6 --stats user@--ip--:/backups/--folder--::'{now:%Y-%m-%dT%H:%M}' /home/pepito
