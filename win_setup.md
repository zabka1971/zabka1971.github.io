# Windows machine environment setup #

## A: Specific considerations for nuc8i7hnk computer ##

Manufacturer's Support Site: [ASUS Support Site](https://www.asus.com/us/supportonly/nuc8i7hnk/helpdesk_download/)

After Window Clean Install reinstall drivers from `\\zabkanas\software\drivers\nuc87hnk\`

## B: Setup standard working environment on Windows machine ##

### Steps during Windows setup ###

1. Windows instance is linked to Microsoft account <roman.miskovsky@gmail.com>
2. OneDrive is activated during Windows setup
3. backed up settings and apps are restored from previous Windows installation

### Important locations ###

User profile folder is `%USERPROFILE%`

OneDrive folder is `%OneDrive%`, its content is being synced against OneDrive

Root backup folder is `%OneDrive%\backup\` - copy everything into it that has to be backed up

### Portable applications ###

All portable applications are located on same drive as Total Commander, drive can be obtained by `%COMMANDER_DRIVE%` (TC pseudo-environment variable)

Global files and setting that should be outside of application folders are located in `%COMMANDER_DRIVE%\_` folder

#### Set environmental variables in batch ####

Batch file `%COMMANDER_DRIVE%\_\set_environment.cmd` creates all environmental variables needed for portable applications [(based on this explanation)](<https://stackoverflow.com/questions/21606419/set-windows-environment-variables-with-a-batch-file>)

### Restore network shortcuts ###

1. copy everything in `%OneDrive%\backup\Network Shortcuts\` into `%APPDATA%\Microsoft\Windows\Network Shortcuts\`

## C: Relevant utilities ##

### Actively used ###

| Utility              | Link                                               | Comment |
| -------------------- | -------------------------------------------------- | ------- |
| Total Commander      | <https://www.ghisler.com/>                         | file manager for Windows run it from %OneDrive%\backup\TotalCMD\Total Commander_from_E.lnk, pin it to taskbar |
| JetBrains Mono       | <https://www.jetbrains.com/lp/mono/>               | a typeface for developers |
| Microsoft 365        | Microsoft Store                                    | |
| [Visual Studio Code](#visual-studio-code)   | <https://code.visualstudio.com/>                   | Code Editing. Redefined |
| [Git](#git)                  | <https://git-scm.com/downloads>                    | --distributed-is-the-new-centralized |
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

## Visual Studio Code ##

1. install from ZIP file
2. activate [VS Code portable mode](https://code.visualstudio.com/docs/editor/portable) by creating `data` folder in installation folder of VS Code (user settings will be in `data\user-data\User\` folder)
3. create `tmp` folder in `data` folder to force temporary files of VS Code to be stored in portable location
4. Put `zabkanas` into Allowed UNCHosts setting - to be able to [work with UNC paths in VS Code](https://stackoverflow.com/questions/76267211/vs-code-cannot-open-unc-path-files-because-of-allowed-unchosts-case-sensitivity) without mapping it to logical drives

## Git ##

1. install from ZIP file, to make Git fully portable continue with next step
2. to avoid global config file to be created in `%USERPROFILE%` create new user environment variable [GIT_CONFIG_GLOBAL](https://git-scm.com/docs/git-config#ENVIRONMENT) (created as part of [batch environment variables setting](#set-environmental-variables-in-batch))
3. set VS code setting variable git.path using double slashes in path name (according to <https://www.diaryfolio.com/2022/01/vs-code-portable-git-shell-integration.html>)

### Useful Git commands ###

[Displaying where GIT configuration settings of all scopes is stored:](https://stackoverflow.com/questions/12254076/how-do-i-show-my-global-git-configuration)

```console
git config --list --show-origin --show-scope
```

[Setting Global Git Username and Email](https://linuxize.com/post/how-to-configure-git-username-and-email/) - prerequisite for commit changes to remote repository

```console
git config --global user.name "Your Name"
git config --global user.email "youremail@yourdomain.com"
```

## to be (re)moved ##

### Foobar ###

1. settings are in %APPDATA%\foobar2000-v2\ folder

### MusicBrainz Picard ###

1. settings are in  %APPDATA%\MusicBrainz\ folder

pushd popd to work with UNC paths in command prompt

The Portable Freeware Collection                                            <https://www.portablefreeware.com/>

GitHub Pages documentation <https://docs.github.com/en/pages>
Writing on GitHub <https://docs.github.com/en/get-started/writing-on-github>

### Create directory Junction ###

1. `mklink /J "%OneDrive%\backup\extra\MKVToolnix" "%LOCALAPPDATA%\bunkus.org\mkvtoolnix-gui"`

### Restore procedure before portable application being used ###

1. Install all relevant applications

2. copy backup of all relevant configuration files into corresponding folders: (run batch file, file to be created)

3. Create symbolic links from all relevant configuration files to dedicated OneDrive folder: run file  %OneDrive%\backup\create_links.bat in elevated command prompt (Run as administrator...)
