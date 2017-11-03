# Plex

## Plex Media Player

[Documentation](https://support.plex.tv/hc/en-us/sections/201360177)

[FAQ](https://support.plex.tv/hc/en-us/sections/201375708)

Set Raspberry Pi3 Embedded PMP clock/time zone

[Original post](http://forums.plex.tv/discussion/212006/pi3-embedded-pmp-clock-time-zone#latest)

1. Connect through SSH (Used Putty) and connect to "PlexMediaPlayer"

User: Root or root

Password: plex

2. nano /storage/.config/autostart.sh

3. rm /var/run/localtime

4. ln -sf /usr/share/zoneinfo/Europe/Bratislava /var/run/localtime

5. Ctrl+x and Yes

6. chmod +x /storage/.config/autostart.sh

7. Reboot Raspberry

## RASPlex

RASPlex: access through WinSCP
IP address: 192.168.1.11 (Raspberry Pi via Wifi)
login: root
password: rasplex

How to setup sound in RasPlex: for current amplifier configuration apply settings from page 4 in the middle

## Plex database

location of Plex database: /volume1/Plex/Library/Application Support/Plex Media Server/Plug-in Support/Databases/com.plexapp.plugins.library.db
File is Sqlite database.
Directory is visible through SSH client only. Use WinSCP.

