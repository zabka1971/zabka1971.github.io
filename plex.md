# Plex

## Music files preparation

If you are just starting with plex and want to **reorganize your files** anyway, I recommend the following approach

    Music /
       Artist /
          Albumartist - Albumtitle /
             1. trackartist - tracktitle.mp3
             2. trackartist - tracktitle.mp3
             ...

and for a multi-disc album:

    Artist /
          Albumartist - Albumtitle /
             Disc 1 /
                1. trackartist - tracktitle.mp3
                2. trackartist - tracktitle.mp3
                ...
             Disc 2 /
                1. trackartist - tracktitle.mp3
                2. trackartist - tracktitle.mp3
                ...

do note the distinction between Albumartist and Trackartist.
There are separate metatags for these. You need to fill both.
This then provides a means to deal with sampler albums:
The typical sampler simply uses as Albumartist Various Artists
And that is what you should use too, since Plex treats 'Various Artists' a little different. (the standard album sorting mechanism is by release year, descending whereas for Various Artists it is alphabetically, ascending)

You can supply your **own artist photos, artist backdrops and album backdrops**.

This however requires that your music files are organised in a folder structure like this:

    Music /
       Albumartistname /
          artist-poster.jpg      <--- a photo of the artist
          artist-background.jpg  <--- a background/wallpaper particular to the artist
          Albumartistname - Albumtitle /
             cover.jpg           <--- album cover
             background.jpg      <--- album background/wallpaper [if not present, inherited from the 'albumartist' level]
             1. Trackartist - Tracktitle.mp3
             1. Trackartist - Tracktitle.txt
             2. Trackartist - Tracktitle.mp3
             2. Trackartist - Tracktitle.lrc
             ...

The graphic files can be in jpg, png, or tbn format. For all filenames there are a few alternative names which can also be used.

The key to custom posters it the ratio...
2:3 for Posters
16:9 for Fanart (Backgrounds)

[Adding Local Lyrics](https://support.plex.tv/hc/en-us/articles/215916117-Adding-Local-Lyrics)

[Local Media Assets - Movies](https://support.plex.tv/hc/en-us/articles/200220677-Local-Media-Assets-Movies)

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
