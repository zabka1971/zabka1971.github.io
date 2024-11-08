# Windows machine environment setup #

## A: Specific considerations for nuc8i7hnk computer ##

Support Site: [ASUS Support Site]

After Window Clean Install reinstall drivers from `\\zabkanas\software\drivers\nuc87hnk\`

## B: Setup standard working environment on Windows machine ##

### Steps during Windows setup ###

1. Windows instance is linked to Microsoft account <roman.miskovsky@gmail.com>

2. OneDrive is activated during Windows setup

3. backed up settings and apps are restored from previous Windows installation

User profile folder is `%USERPROFILE%`

Put small utilities distributed without install into %USERPROFILE%\Tools

OneDrive folder is `%OneDrive%`, its content is being synced against OneDrive

Root backup folder is `%OneDrive%\backup\` - copy everything into it that has to be backed up

1. Install all relevant applications

2. copy backup of all relevant configuration files into corresponding folders: (run batch file, file to be created)

3. Create symbolic links from all relevant configuration files to dedicated OneDrive folder: run file  %OneDrive%\backup\create_links.bat in elevated command prompt (Run as administrator...)

### Restore network shortcuts ###

1. copy everything in %OneDrive%\backup\Network Shortcuts\ into %APPDATA%\Microsoft\Windows\Network Shortcuts\

### Foobar ###

1. settings are in %APPDATA%\foobar2000-v2\ folder

### MusicBrainz Picard ###

1. settings are in  %APPDATA%\MusicBrainz\ folder

## C: Relevant utilities ##

### Actively used ###

| Utility              | Link                                               | Comment |
| -------------------- | -------------------------------------------------- | ------- |
| Total Commander      | <https://www.ghisler.com/>                         | file manager for Windows run it from %OneDrive%\backup\TotalCMD\Total Commander_from_E.lnk, pin it to taskbar |
| JetBrains Mono       | <https://www.jetbrains.com/lp/mono/>               | a typeface for developers |
| Microsoft 365        | Microsoft Store                                    | |
| Visual Studio Code   | <https://code.visualstudio.com/>                   | Code Editing. Redefined |
| Git                  | <https://git-scm.com/downloads>                    | --distributed-is-the-new-centralized |
| LosslessCut          | <https://mifi.github.io/lossless-cut/>             | ultimate cross platform FFmpeg GUI, config file is set to program directory as described in <https://mifi.github.io/lossless-cut/installation.html> |
| MKVToolnix           | <https://mkvtoolnix.download/>                     | Matroska tools for Linux/Unix and Windows forum: <https://help.mkvtoolnix.download/> |
| MKVCleaver           | <https://blogs.sapib.ca/apps/mkvcleaver/>          | front end (GUI) for MKVExtract.exe - more features when compared with gMKVExtractGUI |
| gMKVExtractGUI       | <https://sourceforge.net/projects/gmkvextractgui/> | GUI for mkvextract utility |
| JMkvpropedit         | <https://github.com/BrunoReX/jmkvpropedit>         | Batch GUI for mkvpropedit, requires OPEN JDK from <https://adoptium.net/en-GB/> |
| MKV Muxing Batch GUI | <https://github.com/yaser01/mkv-muxing-batch-gui>  | a robust application for muxing (merging) videos, settings are in %APPDATA%\MKV Muxing Batch GUI\setting.json, so far not known how to change it |
| Subtitle Edit        | <https://www.nikse.dk/subtitleedit>                | free (open source) editor for video subtitles |
| Imagine              | <https://www.nyam.pe.kr/dev/imagine/>              | Freeware Image & Animation Viewer for Windows |
| XnView MP            | <https://www.xnview.com/en/xnviewmp/>              | versatile and powerful photo viewer, image management, image resizer |
| PotPlayer            | <https://potplayer.tv/>                            | install portable as instructed in <https://www.portablefreeware.com/index.php?id=2483>, same method for PotPlayer Codec Pack 64-bit |
| PicPick              | <https://picpick.app>                              | All-in-one design tool for everyone |
| PeaZip               | <https://peazip.github.io/peazip-portable.html>    | free file archiver utility |

### Non-actively used ###

| Utility              | Link                                               | Comment |
| -------------------- | -------------------------------------------------- | ------- |
| Tidal                | <https://listen.tidal.com/>                        | High Fidelity Music Streaming |
| Plex                 | <https://www.plex.tv/>                             | Streaming media service |
| Sysinternals         | <https://learn.microsoft.com/en-us/sysinternals/>  | advanced system utilities |
| File Converter       | <https://www.freeconvert.com/>                     | Easily convert files from one format to another, online |
| Rufus                | <https://rufus.ie/en/>                             | Create bootable USB drives the easy way |
| UniGetUI             | <https://github.com/marticliment/UnigetUI>         | intuitive GUI for the most common CLI package managers for Windows |
| stacher.io           | <https://stacher.io/>                              | A Beautiful, Modern GUI for YT-DLP |
| Advanced IP Scanner  | <https://www.advanced-ip-scanner.com/>             | scans LAN for IP of connected devices |
| Radeon GPU           | <https://drivers.softpedia.com/get/GRAPHICS-BOARD/AMD/Intel-AMD-Radeon-RX-Vega-M-Graphics-Driver-30-0-13037-4001-64-bit.shtml> | |
| Intel HD Graphics    | <https://drivers.softpedia.com/get/GRAPHICS-BOARD/INTEL/Intel-HD-630-CPU-Graphics-Driver-31-0-101-2130.shtml> | |

## to be (re)moved ##

https://code.visualstudio.com/docs/editor/portable

Put zabkanas into Allowed UNChosts setting

Git portable - set git.path using double slashes (according to https://www.diaryfolio.com/2022/01/vs-code-portable-git-shell-integration.html)

pushd popd to work with UNC paths in command prompt
configure GIT - user name and email to be able to commit changes

The Portable Freeware Collection                                            <https://www.portablefreeware.com/>

GitHub Pages documentation <https://docs.github.com/en/pages>
Writing on GitHub <https://docs.github.com/en/get-started/writing-on-github>

### Create directory Junction ###

1. `mklink /J "%OneDrive%\backup\extra\MKVToolnix" "%LOCALAPPDATA%\bunkus.org\mkvtoolnix-gui"`

[ASUS Support Site]: https://www.asus.com/us/supportonly/nuc8i7hnk/helpdesk_download/
